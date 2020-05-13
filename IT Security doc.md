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
     * Do: 
       * The do phase allows the `plan` from the previous step `to be done`. 
       * `Small changes` are usually `tested`, and 
       * data is gathered to see `how effective` the change is.
     * Check: During the check phase, 
       * the `data and results` gathered from the do phase are `evaluated`. Data are `compared to the expected outcomes` to see any  similarities and differences.
       *  The testing process is also evaluated to see `if there were any changes from the original` test created during the planning phase. To see `what changes work better` than others, and if said changes  can be `improved` as well.
     * Act: 
       * This act phase is where a `process is improved`.  
       * Records from the "do" and "check" phases help `identify issues` with the  process. (These issues may include problems, non-conformities,  opportunities for improvement, inefficiencies and other issues that result in outcomes that are evidently less-than-optimal). 
       * Root `causes of  such issues are investigated`, `found and eliminated` by modifying the  process. Risk is `re-evaluated`. 
       * At the end of the actions in this phase,  the `process has better instructions, standards or goals`. `Planning for  the next cycle` can proceed with a `better base-line`. Work in the `next do phase` should `not create recurrence` of the identified issues; if it does, then the action was not effective.
* **Difference between nonrepudiation and authenticity**
  * Authentication verifies who you are (User-ID) while Non-Repudiation verifies what you did (e.g Sending a message).
  * Authenticity is about one party (say, Alice) interacting with another (Bob) to convince Bob that some data really comes from Alice.
  * Non-repudiation is about Alice showing to Bob a proof that some data really comes from Alice, such that not only Bob is convinced, but Bob also gets the assurance that he could show the same proof to Charlie, and Charlie would be convinced, too, even if Charlie does not trust Bob.

# Lec2
## Cryptography

   * **Model of a cryptographic system**
     
       * slide
      * ![image-20200403150608571](img/image-20200403150608571.png)
* **Classical encryption methods?**
   * Substitution
   * Transposition
   * Product cipher
   * Applying multiple substitutions and/or transpositions possible  
* **Differences between public key and symmetric encryption schemes and their respective adv and disadvantage**
   * Symmetric encryption schemes: key is identical for both sender and receiver 
      * Advantage: 
        * Faster
        * Because the key is not transmitted with the data, so if the connection is intercepted, the data is safe
        * Only the system which possesses the secret key can decrypt a message
      * Disadvantage:
        * The secret key must be exchange before the message, and if the attacker can intercept the connection, then any message using that key to encrypt can be decrypted
        * Cannot provide digital signatures that cannot be repudiated
   * Public key: different pair of key for every direction of communication
      * Advantage:
        * There is no need to exchange the private key (which help the recipient to read the encrypted message) so if the connection is intercepted, the message is still safe
        * Can provide digital signatures that cannot be repudiated 
      * Disadvantage:
        * Slower
* **Term of Hybrid encryption scheme and its sequence thereof**
  
   * It's like the mix of symmetric and public key schemes: Hybrid encryption is achieved through data transfer using unique session keys along with symmetrical encryption. Public key encryption is implemented for random symmetric key encryption. The recipient then uses the public key encryption method to decrypt the symmetric key. Once the symmetric key is recovered, it is then used to decrypt the message.
* **Term of "Mode of operation". Outline encrypt and decrypt for at least 2 different modes**
   * Mode of operation is  an algorithm used in conjunction with a block cipher that makes up the complete encryption algorithm
   * Used in CBC, CFM
* **Conditions must be met to conduct brute force attack**
  
  * Length of cipher must longer than key's cipher and key must be finite number of bit
* **What is One time pad? and why it is unbreakable if the encryption key is unknow**
  
  * Use randomness to generate key, and encrypt the message with that random key, so it is uniform distribution
* **How Electronic Code Book (ECB) work. Its adv and disadvantage? When this method can be use **
   * How it works: The user take the first block of plaintext and encrypts it with the key to produce the first block of ciphertext. Then takes the the second block and do the same process and so on
   * ![](img/ecb.PNG)
   * Advantage: Simple to implement, and can be processed in parallel.
   * Disadvantage: Blocks of plaintext go through the same encrypt processes, so the attacker might guess the plaintext if 1 plaintext is sent over and over again. The attacker can also mess up the block order => make the message incorrect
* **How Cipher Block Chaining,Cipher Feedback Mode, Output Feedback Mode, Counter Mode work? **
   * CBC: ![](img/cbc.PNG)
   
   * CFB:![](img/cfb.PNG)
   
     ![](img/cfb2.PNG)
   
   * OFB:![](img/ofb.PNG)
   
     ![](img/ofb2.PNG)
   
   * CM![](img/CM1.PNG)
   
   * ![](img/CM2.PNG)

# Lec3
## Authentication

* **Term of "Authentication" and "Authencity". Factors for it? What is two-factor-authentication**
    	* Authencity: The quality of being genuine or not corrupted from the original. 
    * Authentication: something which validates or confirms the authenticity of something 
    * What you know (Password), What you have (Token), What you are (Biometry)
    * 2-Factor-authentication: provide multiple proof of your identification to get the permission to access.
* **Name and explain on which points the security of password-based authentication schemes depends.**

     * Size of password domain, choice of password and password policies
     * Security of strong passwords
     * Security when entering/transmitting passwords.
* **How secure password should be chosen?(Not sure)**
     * Long password, special character, capital letter, numbers, don't use natural language
* **Describe the sequence in a password-based challenge-response authentication and compare its security with sending the password directly either encrypted or unencrypted.**
* Sequence:![](img/password-based.PNG)
     * Compare: Challenge-response authentication can defend against [session replay attacks](https://whatis.techtarget.com/definition/session-replay-script), in which an attacker listens to previous messages and resends them  later to get the same credentials as the original message.  Challenge-response systems defend against replay attacks, because each  challenge and response is unique. An attacker monitoring credentials  exchanges and then attempting to reuse credentials will not succeed in  gaining access.
* **Describe the terms Token, Smart Card and Biometry and explain their use for authentication**
     * Token: a device that show digits that are changed every minute, can be calculated on the token with some cryptographic embedded in the token which is not ez to extracted
     * Smart card: card that is auth by prove themselves to the card reader that they are really presented by means of cryptography
     * Biometry: physical properties of a person. To prove that you are really you.
* **Describe Cryptographic Hash Functions**
  
  * Compute characteristic pattern (“fingerprint”) of fixed length for each message. Mostly 128 or 256 bits. It should be impossible to find a message producing a given hash value, to find two messages with the same hash value. Widely used algorithms: MD5 and SHA
* **Describe how public key or symmetric cryptography can be used for authentication.**

     * Symmetric key: 
     * ![image-20200424211818767](img/image-20200424211818767.png)
     * Public key: ![image-20200424211900083](img/image-20200424211900083.png)
* **Describe what a digital signature is and how it operates. Also describe how hash functions are used in digital signatures.**

     * A process that guarantees that the contents of a message haven't been altered in transit. Sender signs message with private key. Public key is used for validation
     * Hash function: transforming data of any size into a fixed size. Hash function will  generate unique digital fingerprint. Alice writes a message to Bob, A will hash the message, and then combines the hash value with her private key to generate a digital signature.
* **Explain in detail format, composition and use of certificates. Also describe Certificate Authorities, Root-CA and Certificate revocation.**

     * Format: Bundle of Information of the owner of public key, along with public key, signature of certificate authority (also info about CA).
     * Certificate authority: take the certificate request which consist of  info of the entity (user, web server, ...) along with it's public key, and then it check that this public key is truly belong to that entity. Then CA will sign this certificate with it's private key (compute the hash, then encrypt the hash with private key)
     * Certificate: say B, might not know A but B know its CA and B already had the public key of that CA, so B can check that whether the signature is ok or not. So if B trust this CA, then B can know the public key of A.
     * Root-CA: CA sign its own certificate
     * Certificate revocation: certificate that is no longer valid because that have been withdrawn
* **Discuss advantages and disadvantages of using cerfiticates and CAs.**
     * Advantage: Certificate is public, so anyone can have.
     * Disadvantage: 
       * Trustworthy only given if the root CA and other CA involved in the process are trustworthy
       * CA is compromised and still issuing certificate which might not belong to valid institution
       * Revocation is problematic because sometime this is not checked.

# Lec4
## Operating System Security (this lesson exercise file hasn't covered all the topic in the lecture)

   * **Main tasks of an Operating System and how do they relate to security**
        * Hides complicated details from users and, applications which otherwise had to be dealt with, Provides „Virtual Machine“ which is much easier to use, Allocates resources to different users, processes
* **Explain how the access control mechanisms implemented by an Operating System can be circumventde by an attacker and in which cases it can be enforced**
  * Use admin privilege to access to other individual's information in the organization
* **Explain Linux's access control mechanism in detail**
  * Each file has permission specified for 3 specific type of user (see below)
* **Explain each of the field in ls-l command's return**
  * drwxr-xr-x 2 max staff 4096 Mar 27 12:15 test 

  * d-: file type: directory (l for link)
  * first 3: permission for the owner
  * 3 after: for the group which the file belong to
  * 3 after: for everyone
  * number of link of directories inside this directory
  * user name
  * group name
* **Which permissions are sufficient to execute a file containing a binary? Which permissions are sufficient to execute a shell script?**
  * x
* **Which permissions are needed to copy a file?**
  * source: r, target: w x
* **Which permissions are necessary to move a file?**
  * source: w, target: w x
* **`setfacl` `geftacl` do and explain their practical use in a self-chosen example. What chances do the use of ACLs imply for the commands ls, cp and mv?**
  * `setfacl`: set ACL of files and directory  (ex: Gán quyền đọc , ghi, thi hành cho user bao và group friend: `setfacl -m user:bao:rwx,group:friends:rwx mydir` )
  * `getfacl`: see information of the ACL of the file

# Lec5
## Applications (this lecture dont have exercise)
* **Buffer overflow?**
	![alt text](img/Bufferoverflow.PNG "Logo Title Text 1")
	* Buffer overflow is a vulnerability within the system. with buffer overflow the attacker can inject his own code into the system and execute it. The attacker can gain administrative right to the machine.
	* Applications are executed from assembler code. These programs are not developed in assembler codes but c/c++,... and then are run to a compiler that translate them into assembly language.
	* Resources and memory are allocated for the program. For every function in a program, there is a data frame for the function (include data 4 the function and the address 4 the next function is stored. Because of Von Neumann arch, data and program code are held in the same memory = computer does not distinguish between data and program.
	* Frame for variables are fixed in size, and the program expects inputs, incase the inputs are larger than the memory allocated 4 it, the program might not check for the input is within the boundary or not, which will overflow over to other cells.
	* Results in a change in the return address (overwritten, manipulated) to the inputs and the attacker code gets injected.
	* Not very difficult to protect against bufferoverflow: 
		* Need to check the input does not overflow the expected input.
		* Canaries, a random value b4 return address, which is also stored elsewhere. The value is later checked.
* **Race conditions?**
		![alt text](img/Racecondition.PNG "Logo Title Text 1")
	* Many processes run in parallel on an OS (either in parallel or switching back and forth)
	* Having multiple processes can interupt each other.
	* Application A is running and needs to check for a property 
	* A parallel code of attacker is executed and interupt app A. Which changes the properties that A needed to check.
	* When the execution of A continues, the properties is already manipulated. 
	* Also known as(Race condtions, TOC time of check, TOU time of use error)
	* Can use semaphores or other atoma instructions for the machine for when executions are not interuptable.
* **Active content?**
	* Downloaded file can have malware or undesired functionality. 
	* Can use cryptographic mechanisms to ensure safety (certificates). The program might still contains parts that the issuer is not awared about.

	* Active content: code that you download over the internet, but instead of installing but directly run it e.g: javascript. 
	* Java and java applets: 
		* Java is an interpreter language, it compile codes into java byte code. which is run in java virtual machine. Since virtual machine is an abstract interface, there are libraries. The virtual machines can take on a lot of security functionalities and restrict what the byte code is allowed to do.
		* That is particularly done 4 java applets, which are downloaded from the internet and executed on the local machine.
		* Many think because of this applets are safe, no. There are signed and unsigned applets. Applets can have access to system files. Appplets are also not allowed to open network connections except for where it is downloaded from. Trusted applets are allowed to read and write in system files, but only if they are allowed. 
		* Applets in the past have been compromised. But using applet is safer than running java directly.
	* Also javascript, ActiveX (Microsoft windows)
​    
# Lec8
## Network security

* **Depict potential threats when communicating over a network.**
	* Intercept the traffic between the sender and the receiver, gains access to the info between the two
	* Manipulate: whatever the sender is sending to the receiver, the communication could be changed, altered
	* Spoof: Impersonate the sender, the receiver cannot distinguish between the sender and unauthorized third party
	* Disruption: If you cannot hack it break it. The unauthorizeed third party can disrupt communications.

* **Explain why an attacker might manipulate routing in a network**

attacks are especially simple when the attacker has access to one of the intermediate
stations which relays the communication between the receiver and the receiver. Many of
the attack are based on routing the routing the traffic over a station that is under control of
the attacker.
The structure of the internet makes it simple to do so.
* **Explain the following attacks:**
    * **MAC Address Spoofing**
		MAC Spoofing: Not too diffucult to change MAC address. Certain app use
		the MAC for authentication purposes, like DHCP, WLAN use mac for restricting network access,...
	* **ARP Spoofing**
		![alt text](img/ARPspoofing.PNG "Logo Title Text 1")
		* ARP Spoofing: Address resolution protocol for translating IP to MAC such that within the same LAN segment packets can be routed.
		* If such a translation is necessary, then the protocol will findout whether a MAC address will belong to an IP address.
		* Since you don't want to this all the time so you store it in the ARP cache.
		* Attacker poison/manipulate the ARP cache to their advantage
		* B wants to send packets to C (192.168.5.19)
		* A reply to B that the MAC address for 192.168.5.19 is A's MAC.
		* If A makes sure that C is not listening and responding to B, B will store A's MAC address as the MAC for 192.168.5.19 in its ARP cache.
		* Later on all B packets intended for C will be send to A. 
		* It is a well-known attack.
		* How to prevent: 
			* Have a static arp cache or check regularly whether a machine's arp cache is the same as the others arp cache and is matching with their own IP.
			* Machine can also do ARP queries on its own IP addresses and find out whether somebody else is alreadying responding to this.
	* **IP Spoofing**
		![alt text](img/IPspoofing.PNG "Logo Title Text 1")
		Impersonate an IP address. A impersonates B's IP and send a message to C, C then answers to B without knowing
		about A. B is going to see traffic from C. = ddos attack. A wil not get much of a respond.
	* **TCP Sequence Number Attack**
		![alt text](img/TCPsequenceattack.PNG "Logo Title Text 1")
		* A impersonates C in a 3 way handshake. A (impersonating C) sends SYN to server B
		* B then responds by sending a SYN ACK with sequence number = server to C.
		* C for some reasons does not respond to B (Due to previous attack by A).
		* A then guesses the server sequence number and +1 to it as ACK for the ACK respond and SEQ = client number +1 (previously created by A).
		* A successful connection is establish between A and B if A sucessfully guessed the sequence number.
		* There were a vulnerability to guess a sequence number. 
		* In the past there were trust relationships between machines (no cryptographic...). A could use this to add its IP to B's trust relationships, close the connection and uses the trusted relationship.

    * **Phishing**
	
		Attacker run a service that looks like the bank's service (not the actual bank), someone who connect to this service, all entered credentials are 
		exposed to the attacker. Ways to lure the client to connect to the fake service. Two of them are phishing and pharming. For phishing the client will 
		receive an email, from seemingly the bank, but it is actually from the attacker. Within that email embedded is the link, but the dns name of the bank is not
		included but the link is somehow similar to the bank's. 

    * **Pharming / DNS Spoofing**
	 	![alt text](img/Pharming.PNG "Logo Title Text 1")
		For pharming, the attacker manipulate/poison the dns service protocol. There are vulnerability of the system that can be misused by the attacker. The attacker can
		manipulate the dns server or the machine (but they rather do the machine). So the dns domain would lead the client to the attacker's IP website.

* **Advantages and disadvantages of security mechanisms and protocols on all layers of the network reference model and compare them. Also, give examples for their use.**
	* Application layer security: The application programmer has to take care of all of the security needs of the application (CIA).
		![alt text](img/Applicationlayersec.PNG "Logo Title Text 1")
		* Advantages: Allow to use networks which are completely unsafe, independent of mechanisms of other layers, the protection is truly between the sender and the receiver (end to end).
		* Disadavantages: Complexity of application increases, It is difficult to reuse components within the applications, each and every software may have its own mechanism in the worst case.
		* Examples: Email encryption by the use of certificates, If the user would encrypt a file b4 the file is transmitted.
	* Transport layer security: The unencrypted data is handed over from the application layer to the transport layer, the transport layer transmit the encrypted data is transmitted throug the network, and is decrypted again in the transport layer.
		![alt text](img/Transportlayersec.PNG "Logo Title Text 1")
		* Advantages: Allows transport layer does these things without application layer knowing it in some cases, mechanism which is implemented once can be use by as many applications that like to use it (good reusability)
		* Disadvantages: Not end to end (In case there is/are a server/s that relays information in the middle), we cannot make sure that the whole transport is encrypted, also the data is unencrypted in the middle server.
	* Network layer security: Secure communication between 2 intermidiate stations on the network layer between 2 routers or a router and an endpoint (not end to end), transparent to the above layers.
		![alt text](img/Networklayersec.png "Logo Title Text 1")
		* Advantages: High flexibility (possible to provide security on parts of the communication flow), transparency to the above layers (no changes to above layers to deploy these mechanisms).
		* Disadvantages: Transparancy is also bad because it is impossible or very difficult to intentionally employ these mechanisms.
		* Examples: Virtual network machine
	* Data link layer security: Authentication, authorization and access control
		![alt text](img/Datalinksec.PNG "Logo Title Text 1")
		* Advantage: Allow to control which station are granted access to the Data link layer within the network
		* Disadvantage: solely local protection
		* Examples: Security in wireless LAN, ....
# Lec9
## Firewalls

* **Firewalls:**
	* Place on the position connecting the intranet to the internet and control the traffic between both network according to rules.
	* According to these rules (AKA policies), the firewall distinguishes between allowed and unwanted traffic, and also filter out unwanted traffic.
	* Not all issues are eliminated by the firewall:
		* There might be insiders in the company.
		* There are legitimate station in the intranet that have been compromised. e.g laptops that connect to the intranet and internet everyday that may have contracted malwares.
		* Loopholes and security vulnerability still, that allow access directly the intranet circumventing the firewall for attackers from outside.
		* Security due to design and implementation or insufficient policies.
* **Packet filter:**
	* Is a indispensible component of the firewall. Builtin to one network station of the networking layer (Router)
	* Consists of rule chains, which consist of one or more rules and a default action.
	* Rule specifies a feature a packet can or cannot have, if the packet matches the rule then a specified action is executed, if it does not match then it is compared to the feature of the next rule
	* If there is no match, there is a specified default action which will be then executed.
	* Default action could be discard the packet, forward the packet or jump to another rule chain.
	* Packet filter let the network administrator design their own rule chains for particular tasks.
	* The order of the rules is important
	* Can filter by port number, IP source or destination, IP ranges, which interface that it came in (interfaces that it came in by internet or interfaces that it came in by intranet), transport protocol, flags, date and time,...
	* Static and dynamic packet filtering:
		* Static: only the packet is considered and solely dependent on the packet itself (AKA stateless)
			* Vulnerability: Attacker could spoof a ACK packet and gain information, this can be solved using dynamic packet filters.
		* Dynamic: information from previous packet might be taken into account (AKA stateful)
	* Limitations: 
		* No user specific or application specific filtering possible, they solely see the IP address
		* The only way to identify applications protocols is to use transport layer information (source ports)
		* Fragmentation can be come problematic, some information might not be present in the packet
		* Applications with vary port numbers.
		* Tunneling: some protocol allows for tunneling, some encapsulate information from one protocol to another protocol. With packet filters that take only header information as face value can lead to wrong conclusions.
		* Encryption: once encryption happened, packet filter might have no clue what might actually be in the package
* **application level gateway ?**
	* Component of firewall
	* Not look at packets but get the information on the application level and then filter based on this information
	* AKA proxy for http, session border controller, voice over IP
	* Connection between the station in the intranet and the server in the internet, this connection does not happen directly but instead through a intermidiate station which filters and controls the traffic on the application layer
	* There are rules about what is allowed and not allowed
	* The client send a request to the Application-Level-Gateway then forward the request to the server
	* It can cache website, access control (blocking certain domains), content checking (malware,...), logging all activities, upload/download control.
	* Advantage over packet filters: 
		* User specific rules, could require user to login, after the login there can be roles and rights
		* fine-grained control (communication peers, functions)
		* Checking the content
		* No direct connection between sender and receiver
		* Logging
	* Disadvantages:
		* Very application specific, a ALG for http can only be used for http, also multiple ALGs for many apps
		* Exposed for attack, because they are very visible to the outside
* **demilitarized zone?**
	![alt text](img/DMZ.PNG "Logo Title Text 1")
	* Is a zone which is protected from the internet by a packet filter and also is also seperated from a protected internal network by another packet filter 
	* The first packet filter offer fine-grained control what type of access from the internet to the servers accessible from the Internet
	* The second packet filter offer fine grained control over what type of access is possible from the server accessible from the Internet to the internal network
	* It makes sense to also seperate DMZ such that if one machine in the DMZ is compromised, no other machine in the zone is also compromised
* **How packet filter works**
	Answered above.
* **Network Address Translation is and how it works.**
	![alt text](img/NAT.PNG "Logo Title Text 1")
	* Since private IP addresses cannot be routed in public networks
	* When a packet come to C from A or B, the IP address of A or B is replaced by the public IP of C (N)
	* Packet is then transfer to D or E, what they would see is the address N, and reply to N
	* When the packet arrive at C as N, the packet is somehow determine whether the traffic is meant to be for A or for B and how to then replace the public address by A's or B's private address
	* It is not enough to only translate IP addresses: there must also be a translation of port number
* **inherent weaknesses and vulnerabilities in the concept Firewalls**
	* Mobile devices do not remain in the premises of the company but they would gain access to the network. Outside of the protected network of the institution, these machine are not protected by the firewall, Especially in public network, ppl might setup to infect devices with malwares. These devices can be infected easily and can brought malware to the company.
	* Tunnels and encryption: Are not only threats but can be useful.
		* Tunneling and encapsulation: B and X offer tunneling service
		![alt text](img/Tunneling.PNG "Logo Title Text 1")
		* The administrator will have a hard time trying to allow stuff out of the firewall and not allowing anybody using tunneling
		* The stuff being sent through the tunnel could be encrypted, the proxy have no chance of finding out what is in the tunnel
* **Describe how a static packet filter distinguishes between incoming and outgoing TCP connections. Denote the corresponding rules in pseudo notation or verbally.**
	Based on packets' flags, TCP for example, intranet does not take any SYN from the internet but only the other way around.
* **Describe how a dynamic packet filter distinguishes between incoming and outgoing TCP-connections. Denote the corresponding rules in pseudo notation or verbally.**
	Based on previous packets
# Lec10
## Virtual Private Networks
	There might be people who work outside the company but need access to the intranet. Back in the days, 
	they used direct remote dial-up connection through a modem between a PC from outside the company. Which was
	very costly and doesn't provide the right bandwidth. The usage of this have been reduced thanks to VPN.
	
	Another option is to allocate all the resources which are to be used from the outside, are not shielded by the firewall
	but to put it on the internet. Basically move the server to the DMZ. Problem: If we have a lot of resources which need to be moved,
	meaning a lot of authentication to be dealt with. If we want to check who gets access to our system, we would have to check the log file
	of all the servers. With VPN, it's much easier to check who gets access.
* **VPN? RAS? Site-to-site VPN?**
	![alt text](img/VPN.PNG "Logo Title Text 1")

	* A virtual private network allows to run a secure seemingly direct point to point connection between two stations, similar to a direct line
	between 2 stations. By using (potentially) an unsecured network such as the internet. Can be realized in software as well as hardwell. VPN is like
	a lease private line between 2 stations, but actually a unsecured connection on the internet which emulates this.
	
	* VPN does not have high availability, but there are means of ensuring the confidentiality and integrity of data. Because of this, private lines
	* are still needed to ensure availability.
	
	![alt text](img/VPN2.PNG "Logo Title Text 1")
	
	* VPN can be done by means of tunnelling and encryption:
		* The client R in the internet wants to connect to the server S to use the intranet's resources
		* Client R has according IP address.
		* The VPN (software on the machine) contacts the VPN server (server S), go through a handshake with authentication and negotiation of encryption credentials
		* After having setup the encryption credentials, the server hands out VPN IP address z to the client R (address z belongs to the intranet), all the apps within R would then use the IP-address z to communicate
		* Because R sits outside the intranet, the IP couldn't really be used, so the VPN software take the packet that was created from z to w (IP address of internal server) and encapsulate the packet (encrypt it and put in another packet) which would then be sent to the VPN server
		* The server get the packet, decapsulate the packet and send it in the clear to w from IP address z
		* The internal server is not awared of the VPN usage.
	* Site to site:
		![alt text](img/SitetositeVPN.PNG "Logo Title Text 1")
		* Remarks: R1 and R2 don't know whether there is a VPN or what happens in between, end to end encryption is recommend
* **How IPSec works in detail. In your explanation, the terms AH, ESP, Tunnel Mode and Transport mode should be addressed. Also, describe what the Sequence Number in AH and ESP is used for.**
	* The IP security (IPSec) is an Internet Engineering Task Force (IETF) standard suite of protocols between 2 communication points across the IP network that provide data authentication, integrity, and confidentiality. It also defines the encrypted, decrypted and authenticated packets
	* Components of IP Security:
		* Encapsulating Security Payload (ESP): It provides data integrity, encryption, authentication and anti replay. It also provides authentication for payload.
		* Authentication Header (AH): It provides data integrity, authentication and anti replay and it does not provide encryption. The anti replay protection, protects against unauthorized transmission of packets. It does not protect data’s confidentiality.
		* Internet Key Exchange (IKE): Internet Key Exchange (IKE) provides message content protection and also an open frame for implementing standard algorithms such as SHA and MD5. The algorithm’s IP sec users produces a unique identifier for each packet. This identifier then allows a device to determine whether a packet has been correct or not. Packets which are not authorized are discarded and not given to receiver.
	* Uses of IP Security:
		* To encrypt application layer data.
		* To provide security for routers sending routing data across the public internet.
		* To provide authentication without encryption, like to authenticate that the data originates from a known sender.
		* To protect network data by setting up circuits using IPsec tunneling in which all data is being sent between the two endpoints is encrypted, as with a Virtual Private Network(VPN) connection.
	* How it works:
		* The host checks if the packet should be transmitted using IPsec or not. These packet traffic triggers the security policy for themselves. This is done when the system sending the packet apply an appropriate encryption. The incoming packets are also checked by the host that they are encrypted properly or not.
		* Then the IKE Phase 1 starts in which the 2 hosts( using IPsec ) authenticate themselves to each other to start a secure channel. It has 2 modes. The Main mode which provides the greater security and the Aggressive mode which enables the host to establish an IPsec circuit more quickly.
		* The channel created in the last step is then used to securely negotiate the way the IP circuit will encrypt data accross the IP circuit.
		* Now, the IKE Phase 2 is conducted over the secure channel in which the two hosts negotiate the type of cryptographic algorithms to use on the session and agreeing on secret keying material to be used with those algorithms.
		* Then the data is exchanged across the newly created IPsec encrypted tunnel. These packets are encrypted and decrypted by the hosts using IPsec SAs.
		* When the communication between the hosts is completed or the session times out then the IPsec tunnel is terminated by discarding the keys by both the hosts.
	* Tunnel mode: If there is a security association between 2 stations in tunnel mode, then all packets which are being secured by the SA are being tunneled between the stations. Which means packets to be secured through the association will be encapsulated in another IP packet so there is a new IP header and being tunneled between the system. The IP source and destination are the IP of system which are being connected by the SA.
	* Transport mode: IPsec support end to end encryption of packets. The IP header of the protected packets are not changed by IPSec but the payload either integrity protected or encrypted. Cannot be used for VPN
	* Sequence number in AH and ESP is used for protection against replay attack, this number is incremented for each packets. When the maximum number is reached a new security association must be setup.
* **Explain and describe how OpenVPN works in detail. In your explanation, the terms tun device and tap-device should be addressed.**
	* OpenVPN works by creating virtual interfaces in user space under Linux
	* Set up 2 virtual interfaces, which are point to point interfaces connecting 2 routers. This is how OpenVPN is displayed in the router.
	* In fact there is no point to point connection, but it is encrypted and encapsulated and sent over the public interface by using SSL/TLS transport connection
	* Can be run with TCP and UDP. UDP is likely the best possible choice for transporting because if a frame gets lost, we don't want to stall the whole process untill the frame is received again
	* OpenVPN is very flexible and can transfer traffic either from the network layer as well as from the data link layer:
		* If used on network layer, so called tun device comes in to play
		* If used on data link layer, so called tap device is used



## Lec13

# Network Applications (this lecture dont have file exercise)



* **POP-Auth?**
  * when you fetch a email, you will tell the server your username, the user keyword and the server will rep with the ok. then you will send out the pass phrase (secret) then the server will rep with another ok again, then you are logged in
* **How emails work?**
  * Sender first contact the sender's mail server by a protocol called smtp, then the sender's mail send to recipient's mail server also using smtp protocol, and the mail will be stored in this server. when the recipient want to read the email, the recipient will contact that mail server to get the mail by a protocol called POP/IMAP
* **App layer encryption**
  * before send out the email, convert it to ciphertext and then proceed the normal email sending procedure. When the email is arrived at the final destination and the other end, the email will then be decrypted
* **SSH**
  * The SSH protocol (also referred to as Secure Shell) is a method for secure remote login from one computer to another
  * The protocol works in the client-server model, which means that the  connection is established by the SSH client connecting to the SSH  server. The SSH client drives the connection setup process and uses  public key cryptography to verify the identity of the SSH server. After  the setup phase the SSH protocol uses strong symmetric encryption and  hashing algorithms to ensure the privacy and integrity of the data that  is exchanged between the client and server.
  * ![](img/How_does_the_SSH_protocol_work_.png)
* **Local PFW**
  * connection that transfer from SSH Client to SSH Server to the destination host/server 
  * ![](img/loca_pfw.gif)
* **Remote PFW**
  * connection that transfer from SSH Server to SSH Client to the destination host/server 
  * ![](img/remote_pfw.gif)
* **TLS/SSL**
  * [cryptographic protocols](https://en.wikipedia.org/wiki/Cryptographic_protocol) designed to provide [communications security](https://en.wikipedia.org/wiki/Communications_security) over a [computer network](https://en.wikipedia.org/wiki/Computer_network).
  * Structure: ![](img/tls_ssl_structure.PNG)
  * Lay between Application layer and Transport layer
  * Consist of 2 smaller layer in TLS/SSL protocol: 
    * First 3 protocol for negotiate of the encrypted connection, 4th one for transferring something.
    * TLS Record Protocol: transferring record which are encrypted symmetrical cryptographical mechanism and using digital signature for ensuring integrity of respective record. Then this protocol will be then used by other specified protocol for transmission 
  * How TLS/SSL is used: handshake protocol.
* **Dynamic content**
  * Content that constantly or regularly changes based on user interactions, timing and other parameters that determine what content is delivered to the user (like Facebook)
* **Simple Anonymization**
* **S/MIME**
  *  A standard for [public key](https://en.wikipedia.org/wiki/Public_key) [encryption](https://en.wikipedia.org/wiki/Encryption) and [signing](https://en.wikipedia.org/wiki/Digital_signature) of [MIME](https://en.wikipedia.org/wiki/MIME) ( **MIME** is an [Internet standard](https://en.wikipedia.org/wiki/Internet_standard) that extends the format of [email](https://en.wikipedia.org/wiki/Email) messages to support text in [character sets](https://en.wikipedia.org/wiki/Character_set) other than [ASCII](https://en.wikipedia.org/wiki/ASCII), as well as attachments of audio, video, images, and application  programs.  Message bodies may consist of multiple parts, and header  information may be specified in non-ASCII character sets. Email messages with MIME formatting are typically transmitted with standard protocols, such as the  [Simple Mail Transfer Protocol](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) (SMTP), the [Post Office Protocol](https://en.wikipedia.org/wiki/Post_Office_Protocol) (POP), and the [Internet Message Access Protocol](https://en.wikipedia.org/wiki/Internet_Message_Access_Protocol) (IMAP).) data
  * S/MIME provides the following cryptographic security services for electronic messaging applications:
    - [Authentication](https://en.wikipedia.org/wiki/Authentication)
    - Message integrity
    - [Non-repudiation](https://en.wikipedia.org/wiki/Non-repudiation) of origin (using digital signatures)
    - Privacy
    - Data security (using encryption)
* **PGP**
  * **Pretty Good Privacy** (**PGP**) is an [encryption program](https://en.wikipedia.org/wiki/Encryption_software) that provides [cryptographic](https://en.wikipedia.org/wiki/Cryptographic) [privacy](https://en.wikipedia.org/wiki/Privacy) and [authentication](https://en.wikipedia.org/wiki/Authentication) for [data communication](https://en.wikipedia.org/wiki/Data_communication). PGP is used for [signing](https://en.wikipedia.org/wiki/Digital_signature), encrypting, and decrypting texts, [e-mails](https://en.wikipedia.org/wiki/Email), files, directories, and whole disk partitions and to increase the security of e-mail communications

