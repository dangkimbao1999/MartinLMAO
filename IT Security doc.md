<h1> IT Security </h1>

*Here are the list of information that need to be composed* 

<ol>
    <li>Introduction
    <ul>
        <li>What is the term of security?</li>
        <li>What is the aim of security? Example</li>
        <li>What are passive and active attack?Why those need to be distinct</li>
        <li>Explain security processes and its phases</li>
        <li>Difference between nonrepudiation and authenticity</li>
        <p>Authentication verifies who you are (User-ID) while Non-Repudiation verifies what you did (e.g Sending a message).

Authenticity is about one party (say, Alice) interacting with another (Bob) to convince Bob that some data really comes from Alice.

Non-repudiation is about Alice showing to Bob a proof that some data really comes from Alice, such that not only Bob is convinced, but Bob also gets the assurance that he could show the same proof to Charlie, and Charlie would be convinced, too, even if Charlie does not trust Bob.</p>
    </ul>
    </li>
    <li>Cryptography
    <ul>
        <li>Model of a cryptographic system</li>
        <li>Classical encryption methods</li>
        <li>What are Encryption schemes</li>
        <li>Differences between public key and symmetric encryption schemes and their respective adv and disadv</li>
        <li>Term of Hybrid encryption scheme and its sequence thereof</li>
        <li>Term of "Mode of operation". Outline enrypt and decrypt for at least 2 different modes</li>
        <li>Conditions must be met to conduct brute force attack</li>
        <p>Length of cipher must longer than key and key must be finite number of bit</p>
        <li>what is One time pad? and why it is unbreakable if the encryption key is unknow</li>
        <p>use randomness to generate key, and encrypt the message with that random key, so it is uniform distribution</p>
        <li>How Electonic Code Book (ECB) work. Its adv and disadv? When this method can be use </li>
        <li>How Cipher Block Chaining,Cipher Feedback Mode, Output Feedback Mode, Counter Mode work? </li>
    </ul>
    </li>
    <li>Authentication
    <ul>
        <li>Term of "Authentication" and "Authencity". Factors for it? What is two-factor-authentication</li>
        <p>Authencity: The quality of being genuine or not corrupted from the original. 
Authentication: something which validates or confirms the authenticity of something 
What you know (Password), What you have (Token), What you are (Biometry)
2-Factor-authentication: provide multiple proof of your identification to get the permission to access.</p>
        <li>Name and explain on which points the security of password-based authentication schemes depends.</li>
        <li>How secure password should be chosen?</li>
        <li>Describe the sequence in a password-based challenge-response authentication and compare its security with sending the password directly either encrypted or unencrypted.</li>
        <li>Describe the terms Token, Smart Card and Biometry and explain their use for authentication</li>
        <li>Describe Cryptographic Hash Functions</li>
        <p>Compute characteristic pattern (“fingerprint”) of fixed length for each message. Mostly 128 or 256 bits. It should be impossible to find a message producing a given hash value, to find two messages with the same hash value. Widely used algorithms: MD5 and SHA</p>
        <li>Describe how public key or symmetric cryptography can be used for authentication.</li>
        <li>Describe what a digital signature is and how it operates. Also describe how hash functions are used in digital signatures.</li>
        <li>Explain in detail format, composition and use of certificates. Also describe Certificate Authorities, Root-CA and Certificate revocation.</li>
        <li>Discuss advantages and disadvantages of using cerfiticates and CAs.</li>
    </ul>
    </li>
    <li>Operating System Security (this lesson exercise file hasn't covered all the topic in the lecture)
    <ul>
        <li>Main tasks of an Operating System and how do they relate to security</li>
        <li>Explain how the access control mechanisms implemented by an Operating System can be circumventde by an attacker and in which cases it can be enforced</li>
        <li>Explain Linux's access control mechanism in detail</li>
        <li>Explain each of the field in ls-l command's return</li>
        <li>Which permissions are sufficient to execute a file containing a binary? Which permissions are sufficient to execute a shell script?</li>
        <li>Which permissions are needed to copy a file?</li>
        <li>Which permissions are necessary to move a file?</li>
        <li>`setfacl` `geftacl` do and explain their practical use in a self-chosen example. What chances do the use of ACLs imply for the commands ls, cp and mv?</li>
    </ul>
    </li>
    <li>Applications (this lecture dont have exercise)
    <ul>
        <li>Buffer overflow?</li>
        <li>Race conditions?</li>
        <li>Active content?</li>
    </ul>
    <li>Network security
    <ul>
        <li>Depict potential threats when communicating over a network.</li>
        <li>Explain why an attacker might maipulate routing in a network</li>
        Explain the following attacks:
		 MAC Address Spoofing
		 ARP Spoofing
		 IP Spoofing
		 TCP Sequence Number Attack
		 Phishing
		 Pharming / DNS Spoofing
        <li>Avantages and disadvantages of security mechanisms and protocols on all layers ofthe network reference model and compare them. Also, give examples for their use.</li>
    </ul>
    </li>
    <li>Firewalls
    <ul>
        <li>Firewalls ? Packet filter ? application level gateway ?demilitarized zone? tunnel</li>
        <li>HOw packet filter works</li>
        <li>Network Address Translation is and how it works.</li>
        <li>inherent weaknesses and vulnerabilities in the concept Firewalls</li>
        <li>Describe how a static packet filter distinguishes between incoming and outgoing TCPconnections. Denote the corresopnding rules in pseudonotation or verbally.</li>
        <li>Describe how a dynamic packet filter distinguishes between incoming and outgoing TCP-connections. Denote the corresopnding rules in pseudonotation or verbally.</li>
    </ul>
    </li>
    <li>Virtual Private Networks
    <ul>
        <li>VPN? RAS? Site-to-site VPN?</li>
        <li>how IPSec works in detail. In your explanation, the terms AH, ESP,
Tunnel Mode and Transport mode should be addressed. Also, describe what the Sequence Number in AH and ESP is used for.</li>
        <li>Explain and describe how OpenVPN works in detail. In your explanation, the terms tundevice and tap-device should be addressed.</li>
    </ul>
    </li>
    <li>Network Applications (this lecture dont have file exercise)
    <ul>
        <li>How emails work?</li>
        <li>POP-Auth?</li>
        <li>App layer encryption</li>
        <li>SSH</li>
        <li>Local PFW</li>
        <li>Remote PFW</li>
        <li>TLS/SSL</li>
        <LI>Dynamic content</LI>
        <li>Simple Anonymization</li>
    </ul>
	</li>
</ol>

