# Executable and Linking Format (ELF)

* Collection of headers, segments and sections
* Representation of code and data
* Stored on disk and used to create and start process

# Stack (used for?)

* Lightweight data structure
* Provides functions with static memory (stack frames)
* Not contained within the binary
* Initialized during process startup
* Located at higher end of memory and growing towards lower end
* Maximize space in between

# Stack frame (how can it be used?)

* Contains info about usable memory
* Function's start and end manage each stack-frame
* esp register keeps track of topmost element
* ebp register is used as a reference to point to function arguments and local var
* push instruction to add word-aligned elements
* pop instruction to remove word-aligned elements

# Calling convention (used for?)

- Arg passed via stack
- eip reg passed via stack by CPU
- Function code pushes esp,ebp and other reg
- Results passed back via eax 

# Function call

- khi tạo 1 function thì sẽ add các cái var trong function đó theo stack, theo thứ tự là function->para->return->base  pointer(ebp)->other reg->local var...
- còn trong main sẽ đc fill theo heap

# hack ?

- Attacker controls what is written into buffer
- offset of return with buffer calculatable
- buffer filled with garbage before return
- return points to a callable memory location
- application might crash afterwards
- <img src="C:\Users\dangk\Desktop\DVWA\Function_call.png" style="zoom:67%;" />
- 450 nop-sled (a sequence of [NOP](https://en.wikipedia.org/wiki/NOP_(code)) (no-operation) instructions meant to "slide" the CPU's instruction  execution flow to its final, desired destination whenever the program [branches](https://en.wikipedia.org/wiki/Branch_instruction) to a [memory address](https://en.wikipedia.org/wiki/Memory_address) anywhere on the slide.) (just move to the next one)
- 33 shellcode (malicious code)
- 37 junk data
- 4 new return address into nop-sled
-  https://www.youtube.com/watch?v=1S0aBV-Waeo&t=537s (7:40)
- ![](\img\buffer_overflow.png)

![](img\overflow.png)

What is buffer overflow

what is stack-based buffer overflow

what is a return add and when it is used

what is a payload and how it is used

what is nop-sled and how it is used

# Mitigation

- Randomize specific memory sections at runtime
  - Candidates sections are: .text,.data,...
  - Offsets within sections do not change
  - Sections have to opt-in
  - Compilerflags to support it
  - Drawback: Only randomize sections. Offsets within section are maintained. Thus leakage of specific pointers can defeat ASLR
  - 32 bits total add
  - Page alignment:12 bits
  - User space
  - mem partition 1 2 3
  - redunction: stack stored in partition one or 2, so effectively 1 bit to guess
  - ->32 - 12 - 1 = 19 bits to guess
- Non excutable: specific segments can be marked as NX
  - Interrupts triggered if such a sections gets executed - > segmentaion fault
  - cpu has to support it
  - compilerflags to support it
  - Draw: do not protected against return oriented approaches
- Stack canaries
  - Magic values placed on stack before stack var
  - Changes with each process invocation
  - Can be checked when leaving functions to prove stack integrity
  - Compilerflags to support it
  - Draw: can potentially leaked, guessed or brute force
- What to do: 
  - use mitigation
  - safe function
  - bounds checking
  - memory-safe programming lang (rust)
  - utilize code analysis (static, dynamic, fuzzing)
  - use modern cpu extension (intel memory protection extensions, control flow enhancement technology)
  - 