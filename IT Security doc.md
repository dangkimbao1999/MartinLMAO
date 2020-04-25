<h1> IT Security </h1>

*Here are the list of information that need to be composed* 

# Lec1
## Introduction



   * **What is the term of security?**
           * Protection of information and information systems against `unauthorized access` and `modification` and `availability` of information system services for `legitimate users`, including measures to thwart, discover or log threats. Protection against unauthorized access must be ensured during `storage`,` processing` or `in transit`
* **What is the aim of security? Example**
    * Confidentiality: Against unauthorized access
    * Integrity: Against unauthorized modification
    * Availability: Resources and services are available for legit users
    * Authenticity and authentication:  Explicit identification of the sender of info or a communication peer
* **What are passive and active attack?Why those need to be distinct**
     * Passive
          * Attacker doesn't actively participate
          * Difficult to discover
          * Preventive means of protection against active attacks (?)
     * Active
          * Attacker actively participate
          * Manipulate data or systems
          * Attacker often leaves traces
          * Prevention and Detection is possible
     * Why distinct these 2 type of attack? **not sure**
          * Because each of these attack focus on different basis, perform diff task, cause different type of damage and and focus on different IT-Security aim. => need to differentiate to have suitable method to prevent those attack
* **Explain security processes and its phases** (not sure)
     * Plan: Establish `objectives and processes` required to deliver the `desired results`.
     * Do: The do phase allows the `plan` from the previous step `to be done`. `Small changes` are usually `tested`, and data is gathered to see `how effective` the change is.
     * Check: During the check phase, the `data and results` gathered from the do phase are `evaluated`. Data are `compared to the expected outcomes` to see any  similarities and differences. The testing process is also evaluated to see `if there were any changes from the original` test created during the planning phase. To see `what changes work better` than others, and if said changes  can be `improved` as well.
     * Act: This act phase is where a `process is improved`.  Records from the "do" and "check" phases help `identify issues` with the  process. These issues may include problems, non-conformities,  opportunities for improvement, inefficiencies and other issues that result in outcomes that are evidently less-than-optimal. Root `causes of  such issues are investigated`, `found and eliminated` by modifying the  process. Risk is `re-evaluated`. At the end of the actions in this phase,  the `process has better instructions, standards or goals`. `Planning for  the next cycle` can proceed with a `better base-line`. Work in the `next do phase` should `not create recurrence` of the identified issues; if it does, then the action was not effective.
* **Difference between nonrepudiation and authenticity**
  * Authentication verifies who you are (User-ID) while Non-Repudiation verifies what you did (e.g Sending a message).
  * Authenticity is about one party (say, Alice) interacting with another (Bob) to convince Bob that some data really comes from Alice.
  * Non-repudiation is about Alice showing to Bob a proof that some data really comes from Alice, such that not only Bob is convinced, but Bob also gets the assurance that he could show the same proof to Charlie, and Charlie would be convinced, too, even if Charlie does not trust Bob.

# Lec2
## Cryptography

   * **Model of a cryptographic system**
* **Classical encryption methods?**
* **What are Encryption schemes?**

   * **Differences between public key and symmetric encryption schemes and their respective adv and disadvantage**
* **Term of Hybrid encryption scheme and its sequence thereof**
* **Term of "Mode of operation". Outline enrypt and decrypt for at least 2 different modes**
* **Conditions must be met to conduct brute force attack**
  * Length of cipher must longer than key and key must be finite number of bit
* **What is One time pad? and why it is unbreakable if the encryption key is unknow**
  * Use randomness to generate key, and encrypt the message with that random key, so it is uniform distribution
* **How Electonic Code Book (ECB) work. Its adv and disadv? When this method can be use **
* **How Cipher Block Chaining,Cipher Feedback Mode, Output Feedback Mode, Counter Mode work? **

# Lec3
## Authentication

    * **Term of "Authentication" and "Authencity". Factors for it? What is two-factor-authentication**
        	* Authencity: The quality of being genuine or not corrupted from the original. 
	* Authentication: something which validates or confirms the authenticity of something 
	* What you know (Password), What you have (Token), What you are (Biometry)
	* 2-Factor-authentication: provide multiple proof of your identification to get the permission to access.
   * **Name and explain on which points the security of password-based authentication schemes depends.**
* **How secure password should be chosen?**
* **Describe the sequence in a password-based challenge-response authentication and compare its security with sending the password directly either encrypted or unencrypted.**
* **Describe the terms Token, Smart Card and Biometry and explain their use for authentication**
* **Describe Cryptographic Hash Functions**
  * Compute characteristic pattern (“fingerprint”) of fixed length for each message. Mostly 128 or 256 bits. It should be impossible to find a message producing a given hash value, to find two messages with the same hash value. Widely used algorithms: MD5 and SHA
* **Describe how public key or symmetric cryptography can be used for authentication.**
* **Describe what a digital signature is and how it operates. Also describe how hash functions are used in digital signatures.**
* **Explain in detail format, composition and use of certificates. Also describe Certificate Authorities, Root-CA and Certificate revocation.**
* **Discuss advantages and disadvantages of using cerfiticates and CAs.**

# Lec4
## Operating System Security (this lesson exercise file hasn't covered all the topic in the lecture)

   * **Main tasks of an Operating System and how do they relate to security**
* **Explain how the access control mechanisms implemented by an Operating System can be circumventde by an attacker and in which cases it can be enforced**
* **Explain Linux's access control mechanism in detail**
* **Explain each of the field in ls-l command's return**
* **Which permissions are sufficient to execute a file containing a binary? Which permissions are sufficient to execute a shell script?**
* **Which permissions are needed to copy a file?**
* **Which permissions are necessary to move a file?**
* **`setfacl` `geftacl` do and explain their practical use in a self-chosen example. What chances do the use of ACLs imply for the commands ls, cp and mv?**

# Lec5
## Applications (this lecture dont have exercise)
   * **Buffer overflow?**
buffer overflow is a vulnerability within the system. with buffer overflow the attacker can
inject his own code into the system and execute it. The attacker can gain administrative
right to the machine. 
Applications are executed from assembler code. These programs are not developed in 
assembler codes but c/c++,... and then are run to a compiler that translate them into 
assembly language. Resources and memory are allocated for the program. We jump
into a function in that program, and there is a data frame for the function (include data 4 the function
and the address 4 the next function is stored. Because of Von Neumann arch, data and
program code are held in the same memory = computer does not distinguish between
data and program. Frame for variables are fixed in size, and the program expects inputs,
incase the inputs are larger than the memory allocated 4 it, the program might not check
for the input is within the boundary or not, which will overflow over to other cells. Results
in a change in the return address (overwritten, manipulated) to the inputs and the attacker
code gets injected.
Not very difficult to protect against bufferoverflow, need to check the input does not overflow
the expected input. Also canaries, a random value b4 return address, which is also stored 
elsewhere. The value is later checked.
* **Race conditions?**
Many processes run in parallel on an OS (either in parallel or switching back and forth)
Having multiple processes can interupt each other. Application A is running and needs to
check for a property, a parallel code of attacker is executed and interupt app A. Which changes
the properties that A needed to check. When the execution of A continues, the properties is
already manipulated. (Race condtions, TOC time of check, TOU time of use error)

Can use semaphores or other atoma instructions for the machine for when executions are
not interuptable.
* **Active content?**


Downloaded file can have malware or undesired functionality. Can use cryptographic mechanisms
to ensure safety (certificates). The program might still contains parts that the issuer is not awared
about.

Active content: code that you download over the internet, but instead of installing but directly run it.
e.g: javascript. 
Java and java applets: Java is an interpreter language, it compile codes into java byte code.
which is run in java virtual machine. Since virtual machine is an abstract interface, there are 
libraries. The virtual machines can take on a lot of security functionalities and restrict what
the byte code is allowed to do. That is particularly done 4 java applets, which are downloaded
from the internet and executed on the local machine. Many think because of this applets are safe,
no. There are signed and unsigned applets. Applets can have access to system files. Appplets are
also not allowed to open network connections except for where it is downloaded from. Trusted applets
are allowed to read and write in system files, but only if they are allowed. 
Applets in the past have been compromised. But using applet is safer than running java directly.

Also javascript, ActiveX (Microsoft windows)
​    
# Lec8
## Network security

   * **Depict potential threats when communicating over a network.**
* **Explain why an attacker might manipulate routing in a network**
* **Explain the following attacks:**
     * **MAC Address Spoofing**
     * **ARP Spoofing**
     * **IP Spoofing**
     * **TCP Sequence Number Attack**
     * **Phishing**
     * **Pharming / DNS Spoofing**
* **Advantages and disadvantages of security mechanisms and protocols on all layers of the network reference model and compare them. Also, give examples for their use.**

# Lec9
## Firewalls

   * **Firewalls ? Packet filter ? application level gateway ?demilitarized zone? tunnel**
* **How packet filter works**
* **Network Address Translation is and how it works.**
* **inherent weaknesses and vulnerabilities in the concept Firewalls**
* **Describe how a static packet filter distinguishes between incoming and outgoing TCP connections. Denote the corresponding rules in pseudo notation or verbally.**
* **Describe how a dynamic packet filter distinguishes between incoming and outgoing TCP-connections. Denote the corresponding rules in pseudo notation or verbally.**

# Lec10
## Virtual Private Networks

   * **VPN? RAS? Site-to-site VPN?**
   * **How IPSec works in detail. In your explanation, the terms AH, ESP, Tunnel Mode and Transport mode should be addressed. Also, describe what the Sequence Number in AH and ESP is used for.**

        * **Explain and describe how OpenVPN works in detail. In your explanation, the terms tun device and tap-device should be addressed.**
    ## Lec13
    # Network Applications (this lecture dont have file exercise)

   * **How emails work?**
* **POP-Auth?**
* **App layer encryption**
* **SSH**
* **Local PFW**
* **Remote PFW**
* **TLS/SSL**
* **Dynamic content**
* **Simple Anonymization**

