- [Introduction](#introduction)
- [Threat and Vulnerability Landscape](#threat-and-vulnerability-landscape)
  - [Asset Selection](#asset-selection)
  - [Threat Modeling and Risk Assessment](#threat-modeling-and-risk-assessment)
    - [Selecting Security Controls](#selecting-security-controls)
  - [Drawbacks](#drawbacks)
  - [Security Attributes (CIA triad)](#security-attributes-cia-triad)
    - [CIA Triad - does not](#cia-triad---does-not)
    - [6 Atomic Elements](#6-atomic-elements)
    - [SABSA Business Attributes](#sabsa-business-attributes)
  - [Defense in Depth](#defense-in-depth)
    - [Types of Defense](#types-of-defense)
  - [Zero Trust Model](#zero-trust-model)
- [Current Threat and Vulnerability Landscape](#current-threat-and-vulnerability-landscape)
  - [Current Threat Landscape](#current-threat-landscape)
  - [Malware (Not a Strict Taxonomy)](#malware-not-a-strict-taxonomy)
    - [Prevalent Malware](#prevalent-malware)
    - [Newer Malware](#newer-malware)
  - [Darknet](#darknet)
  - [Government Activity](#government-activity)
    - [Active Surveillance](#active-surveillance)
  - [Trust and Backdoors](#trust-and-backdoors)
  - [Censorship](#censorship)
- [Basic Encryption](#basic-encryption)
  - [Symmetric Encryption](#symmetric-encryption)
  - [Asymmetric Encryption/Public Key Encryption](#asymmetric-encryptionpublic-key-encryption)
  - [Hash Functions (Establishment of Integrity/Authenticity)](#hash-functions-establishment-of-integrityauthenticity)
  - [Digital Signature](#digital-signature)
  - [Secure Sockets Layer and Transport Layer Security (SSL/TLS)](#secure-sockets-layer-and-transport-layer-security-ssltls)
  - [SSL Stripping](#ssl-stripping)
  - [HTTPS](#https)
  - [Digital Certificates](#digital-certificates)
  - [Certificate Authorities and HTTPS](#certificate-authorities-and-https)
  - [End-to-End Encryption](#end-to-end-encryption)
  - [Steganography](#steganography)
  - [What Attackers go After](#what-attackers-go-after)
- [OS Security \& Privacy](#os-security--privacy)
  - [Virtual Machines (Platform Virtualization):](#virtual-machines-platform-virtualization)
    - [Type 1 (Bare Metal)](#type-1-bare-metal)
    - [Type 2 (Hosted)](#type-2-hosted)
  - [Security Features and Functionality](#security-features-and-functionality)
    - [Security Features](#security-features)
      - [Windows](#windows)
      - [MacOs](#macos)
      - [Linux](#linux)
      - [Android](#android)
      - [iOS](#ios)
  - [Security Bugs and Vulnerabilities](#security-bugs-and-vulnerabilities)
  - [Usage Share](#usage-share)
  - [Windows - Potentially Outdated](#windows---potentially-outdated)
    - [Windows 10](#windows-10)
    - [Windows 7, 8, 8.1](#windows-7-8-81)
  - [Mac OS X - BSD derivative](#mac-os-x---bsd-derivative)
  - [Linux and Unix-like Distribution](#linux-and-unix-like-distribution)
    - [Basing Operating System for Base Level Privacy](#basing-operating-system-for-base-level-privacy)
  - [OS General Classifications](#os-general-classifications)
    - [General Use](#general-use)
    - [General Use w/ Focus on Security and Privacy](#general-use-w-focus-on-security-and-privacy)
    - [Pure Security Focused](#pure-security-focused)
    - [Anonymity Focused](#anonymity-focused)
    - [Mobile OS with Security and Privacy](#mobile-os-with-security-and-privacy)
- [Security Bugs and Vulnerabilities](#security-bugs-and-vulnerabilities-1)
  - [Patching](#patching)
- [Reducing Threat Privilege](#reducing-threat-privilege)
- [Social Engineering and Social Media Offence and Defense](#social-engineering-and-social-media-offence-and-defense)
  - [Information Disclosure and Identity Strategies](#information-disclosure-and-identity-strategies)
    - [Strategies (Precedence is in Desc Order)](#strategies-precedence-is-in-desc-order)
  - [Identify Verfication and Registration](#identify-verfication-and-registration)
  - [Behavioural Security Controls Against Social Threats](#behavioural-security-controls-against-social-threats)
    - [Behavioural Changes (Actions by People)](#behavioural-changes-actions-by-people)
    - [Technical Security Controls](#technical-security-controls)
- [Security Domains](#security-domains)
  - [Physical Security Domain](#physical-security-domain)
  - [Virtual Security Domain](#virtual-security-domain)
- [Security Through Isolation and Compartmentalization](#security-through-isolation-and-compartmentalization)
  - [Intro Isolation and Compartmentalization](#intro-isolation-and-compartmentalization)
  - [Physical Security Isolation:](#physical-security-isolation)
  - [Types:](#types)
    - [MAC Address:](#mac-address)
    - [CPU:](#cpu)
    - [Motherboard:](#motherboard)
    - [Hard Drives:](#hard-drives)
    - [Mitigating Against Serial IDs:](#mitigating-against-serial-ids)
  - [Virtual Isolation:](#virtual-isolation)
    - [Encryption and Compartmentalization:](#encryption-and-compartmentalization)
    - [Dual Booting:](#dual-booting)
    - [Sandboxes: a container that protects the contents inside the container from spilling out](#sandboxes-a-container-that-protects-the-contents-inside-the-container-from-spilling-out)
    - [Portable Apps: self contained applications and do not require installation](#portable-apps-self-contained-applications-and-do-not-require-installation)
  - [Virtual Machines:](#virtual-machines)
    - [Virtual Machine Weaknesses:](#virtual-machine-weaknesses)
    - [Virtual Machine Hardening:](#virtual-machine-hardening)


# Introduction 
- __CanaryTokens__: "Token" attached to a file that notifies you of when that file is opened.
  - Use case: always know when and who opened a file
  - Limitations: If the file does not require an internet connect to open then the actor can open the file offline and you will not be notified
  - Potential: Create own service that creates some form of persistent HTTP/HTTPS request that does not stop attempting until it has a sent the request. Ideally this would be sent/analyzed by some logger that would be regularly parsed through

# Threat and Vulnerability Landscape
- Security is hardly ever the end goal. It is an enable of business. It allows us to do what we like without impediment
  - Only protect is valuable to you - context dependent
  - Only protect them to the extent of their value. If they are not very valuable then you should not spend a copious amount of money on its protection
- __Privacy__: about content - confidentiality, knowing who did it but not knowing the action
- __Anonymity__: about removal of identity from the activity - non-attribution from an action - knowing the action but not knowing who did it/anyone could have done it
- __Pseudoanonymity__: Reputation against an identity - alias/false identity
- Assets: The things that we wish to protect
- Security: The degree to which assets are resistent to threats from adversaries (Technology, Actions, Processes)
  - Threats are leveraged by adversaries
  - Threats exploit vulnerabilities in the security controls
- Security is not done in isolation - security should only be decided by the gravity of the threat landscape
## Asset Selection
- Assets are decided by the entity
  - Valuable is relative/subjective
  - This includes to the granularity of asset definitions

## Threat Modeling and Risk Assessment
- 100% security does not exist
- 0% risk does not exist
  - Engagin in the activity guarantees the risk
- There needs to be an understanding of how much risk can be tolerated
- There is trade off between usability and security
- Risk-based approach should be taken for deciding security
  - Risk = (Vulnerability x Threats x Consequences)
  - Have an understanding of the consequences of threats being realized 
### Selecting Security Controls
- Select Controls: That best mitgate the risk
- Implement: the control
- Assess: the effectiveness of the implemented control 
- Monitor: the control for its prolonged effectiveness

## Drawbacks
- Having "it all" may not be possible: The amount of privacy and anonymity you require is directly proportion to the amount of security needed and there is a trade-off between security and usability
- "Privacy is about controlling how we present ourselves

## Security Attributes (CIA triad)
- Non-repudiation: One party of a transaction means the sender cannot deny sending the message
- Authentication: Verify the identity of the entity/system
- Authorization: Upon authentication, determines what the entity/system is allowed to access
### CIA Triad - does not 
- Confidentiality: Not wanting the assets disclosed to other entities
- Integrity: Ensuring the completeness of the assets over the asset's lifetime
- Availability: The asset is available when it is needed

### 6 Atomic Elements
- Confidentiality: Not wanting the assets disclosed to other entities
- Possession: Loss of ownership but does not include the loss of confidentiality
- Integrity: Ensuring the completeness of the assets over the asset's lifetime
- Authenticity: veracity of ownership
- Utility: usefulness
- Availability: The asset is available when it is needed

### SABSA Business Attributes
- User Attributes
- Management Attributes
- Operational Attributes
- Risk Management Attributes
- Legal/Regulatory Attributes
- Technical Strategy Attributes
- Business Strategy Attributes

## Defense in Depth
- Providing layers of defense so if one fails there is still something defending 

### Types of Defense
- Prevention: Stopping access
- Detection: 
- Recovery: Backups

## Zero Trust Model
- Minimizing the amount that is trusted
- Everything presents a level of risk
  - Trust needs to be evaluated and distributed 
- Consider making us of the Zero Knowledge Systems
  - Zero Knowledge System: Have no information about what they are hosting for their clients

# Current Threat and Vulnerability Landscape
- The issue is that direct human target is problematic but not as common for the normal person. There is software that actively hunts for vulernable/expoitable system, which makes everyone vulnerable
- APT: Advanced Persistent Threat - Specific organization/Person/State attempting to leverage a threat against an owned security control
- The value of a hack or exploitation is not strictly money
  - Hosting from another computer
  - Crypto-mining
  - Collecting information
  - Software keys
  - Forwarding information through your system to further obsfucate their malicious activities
- Cyber criminals are more likely to choose newer technology
  - Adoption of prevention technology is slow because of the necessity of vetting its performance, thus the defensive side of cybersecurity will nearly always be behind technologically from the offensive side
- Security Bug = Vulnerability
  - Known Bugs: have patches - important to say up to day
  - Unknown Bugs(Zero Days) - No Patches

## Current Threat Landscape
- Hacker/Cracker/Cyber Criminal:
  - White hat(): Hacking for good
  - Black Hat: Cyber Criminals (Could be organizations)
  - Script Kiddies: Purchase from legitimiate hackers - perform sophisticated techniques without the knowledge of how the technique works (Can still be dangerous)
- IRC: Internet Relay Chat - text-based chat system for instant messaging (does allow for private one-on-one communications)
  - IRC Channel: group communication using IRC

## Malware (Not a Strict Taxonomy)
- Macro Viruses: Virus written in a macro language - typically platform independent
- Stealth: Hide modifications they have made
- Polymorphic: Copies of self that are difficult to detect with signatures as the virus changes parts of itself during the cloning process
- Self-Garbling Virus: computer virus the hides from anti-viruses by distorting its own code
- Bots & Zombies
- Worms: Move between machines
- OS RootKits: embedded in the kernal or OS
- Firmware Rootkit:
  -  One of the worst the get rid of
- Keyloggers: Log the keys that are pressed 
- Trojan Horse: Appear to be one thing but are another thing
- Remote Access Tool (RATS): Allows compromiser to access the resources of the system remotely
- Spyware: Gather information and send it back to the spy
  - Intelligence gathering malware
- Adware: Software that forces ads
- Scareware: Social engineering attack that is used to trick people thinking something exist that does not
- Potentially Unwanted Programs (PUPs): Catch all terms
- Phishing: Attempt to trick victim to click on link or execute malware
  - Most common attack - easy to set up
  - Common Vector: Emails
  - Typically done en mass
  - Spear Phishing: Specific attack on an entity/person
  - Techniques:
    - Link Manipulation (Real Domain is Left of High-Level Domain [com,net,org,co.uk,etc.]):
      - Using subdomains to obsfucate https://www.google.com.greyson.org
      - Using subdirectories to obsfucate https://www.greyson.com/google.com/store
      - Misspelling words with similar characters https:/rnicrosoft.com - "rn" is used NOT "m"
      - International Domain Name Standard(IDN) Attack: www.g00gle.com
      - Hidden URLs: Using <a></a> in html to obsfucate what is being clicked on
    - Cross-Site Request Forgery: malicious site sends a request to vulnerabille site where the user is currently logged in
    - Cross-Site Scripting: vulnerability in a web application that allows a third party to execute a script in the user's browser on behalf of the web application
  - Variants:
    - Vishing: Phone/Voice Phishing
    - Smshing: Text Message Phishing
- Spam: unsolicited messagesa
  - Low barriers to entry
- Doxing: Research on an individual with the intention of making that private information public or threatening to release public information
- Social engineering: attacks that focus on the weaknesses in people
  - Common Types: Phishing, Lottery Scams (Advanced Fee Fines), Posing as Buyers, Technical Support (Fix Technical Problem), Financial Ad Scams, Online Dating Scams, Fake Friend Scams, etc. 

### Prevalent Malware
- Ransomeware: Taking control of system and encrypting file/systems 
  - Options: 
    - Crack encryption
    - Lose Files
    - Pay Ransom
- Malvertisement: Open ad that is affected with the malware
- Drive-by Attack: Visiting a website that has code injected that is made to exploit your machine

### Newer Malware
- CPU Hijackers: Using the CPU/GPU of others to mine for cryptocurrencies - use CPU cycles
  - Mining = Validation of a transaction = Money maker
  - Vectors: Javascript- Based, Phishing Attacks, Browser, Websites, Untrusted Code, Bad App from Store
  - Mitigation: Monitor the CPUs and GPUs and match against the machine's baseline if one has been established

## Darknet
- Surface Web = Clear Web = does not require special accessible
- Darknet: General term for overlay network that can only accessed with specific knowledge/software/protocol
  - Privacy/Anonymity Enhanced Network
  - Lowers the barrier to entry to be a cybercriminal
  - Many people have sophiscated tools but lack the knowledge to actually create them

## Government Activity
- Five Eyes: Gather and Analyze information from other coutnries and share them amongst each other to reduce the amount that the country itself monitors its own citizens
  - Austrailia
  - Canada
  - New Zealand
  - United Kingdom
  - United States
- Nine Eyes:
  - Denmark
  - France
  - Netherlands
  - Norway
- Fourteen Eyes:
  - Belgium
  - Germany
  - Italy
  - Spain
  - Sweden

### Active Surveillance
- Tools for active or passive surveillance is made available to many governments and well-resourced organizations and entities
  - Think Ant Catalog
- Interdiction:
  - Specific Interdiction: the placement of a control before you purchase/using the equipment
  - General Interdiction: Already available exploitable control

## Trust and Backdoors
- Complexity and security are inversely related
- Formal Methods: mathematically based techniques for the specification, development and verification of software and hardware systems
  - Time Consuming and Cost Prohibitive
- Backdoor: Weakening of a system
  - Closed-Source Environment:
    - Requirement of trusting the developer
    - The only way to determine a backdoor is to do reverse engineering
  - Open-Source Environment:
    - Believed to have less of chance of a backdoor
  - Simple vulnerabilities can create a backdoor
  - Everything can be a target for a potential backdoor
  - Once security is weakened it is weakened for everyone
- Some people do not trust the NIST or NSA standards
- __Reproducible Build__: set of software development practices which creates a verifiable path from human readable source code to the binary code uses by computers
  - Deterministic Building Processes

## Censorship
- Exists everywhere

# Basic Encryption
- Encryption: Method of transforming plain-text to cipher text
- Decryption: Method of transforming cipher text to plain-text
- Brute-Force Attack: Guess all combination/permutations for passwords to get the key
- Dictionary Attack: Use a dictionary to crack the key
- Brute-Force/Dictionary Attack: use an understanding of the target to define the dictionary criteria 
- Symmetric:
  - Fast
  - Strong
- Asymmetric:
  - Better key distribution
  - Better Scalability
  - Can guarantyee Authentication and Nonrepudiation
  - Slow
  - Mathematically intensive
- Cipher Suite: The combination of Encryption technologies used 
  - May not be compatible for all browserss

## Symmetric Encryption
- Components:
  - Algorithm:
    - Publicly Known
  - Key: 
    - Secret
- Advanced Encryption Standard (AES) is a symmetric algorithm
  - Passowrd becomes key
  - 256-bit/128-bit (Bit Length) = Strength of algorithm - effects the duration of encryption/decrypt
    - Also defines keyspace: Number of total possible different keys for the algorithm

## Asymmetric Encryption/Public Key Encryption
- Components:
  - (Generally higher Bit lengths)
  - 2 Keys (Public key and Private key)
- Types:
  - __Rivest-Shamir-Adleman__ (RSA): Strength comes from the difficulty of finding the factors of large prime numbers (Prime factorization problem)
  - __Elliptic Curve Cryptosystem__ (ECC): Computing discrete algorithms of ellipitic curves
  - __Diffie-Hellman__ (DH): Computing discrete algorithms in a finite fields
    - Popular becauses of Forward Secrecy
  - __El Gamal__: Comes from computing discrete algorithms in a finite fields
- Process:
  - One Key encrypts the other key decrypts
    - If encrypt public then private is used to decrypt
      - Only the owner of the private key can decrypt the message - guarantees the only the receiver can read it (Any one could have sent it) - Confidentiality Guaranteed
    - If encrypt with private key then public can decrypt
      - Any can decrypt the message but it ensures that everyone knows who sent it (Authentication)

## Hash Functions (Establishment of Integrity/Authenticity)
- Process: Input -> Crypographic Hash Function -> Digest(Hash)
  - Property of Hash Function (One-Way Encryption): You cannot convert back to the input using the same hash function
    - Hash function provides an output of a fixed length, which is defined by the function being used
    - Types of Hash Functions (Algorithms)
      - MD2/4/5
      - HAVAL
      - SHA1/256/384/512
- Purpose: provide a method of establishing legimacy for the message being sent
- Hash cannot provide evidence for intention modification (e.g. if the cyber criminal augment records that established your baseline - changing the source file and checksum)
- Hash Usages:
  - Password Hashes 
  - Hash Message Authenication Code

## Digital Signature
- Definition: A hash value that is encrypted with the sender's private key - establishes authentication/nonrepudiation/integrity
  - Integrity: guaranteed by the use of the hashing algorithm
  - Nonrepudcation: guaranteed by the use of the sender's private key 
  - Authentication: guaranteed by the use of the sender's private key
- Validating Digital Signature: Decrypt using the public key of the sender and compare the hash value to the one sent 

## Secure Sockets Layer and Transport Layer Security (SSL/TLS)
- SSL(New):
  - Used frequently on older sites for compatible reasons
- TSL(Old):
  - Encrypts the data when communicating between applications
  - There are many ways of Exchange keys and establishing the agreement
    - The best are the ones that support Forward Secrecy
    - __Forward Secrecy__: Gives assurance that the session key will not be compromised even if the private key of the server machine is 
      - Unique session key for each connection
  - Guarantees:
    - Confidentiality (Privacy): Symmetric algorithm is used to encrypt data that is transmitted, keys are generated unique for each connection, which are based on a secret that is established at the start of the session. 
      - Shared Secrets are not vulnerable to a MITM Attack
    - Authenticated: By Digital Signatures and is generally required by at least one of the parties, typically the server
    - Integrity: Each message transmitted is put through a message integrity check - Message Authentication Code (MAC) to prevent undetected loss or alteration of the data during transmission
  - Asymmetric Algorithms are typically used for the establishment of Session Keys (e.g. Diffie-Hellman)
  - Symmetric Keys are used for the transmission of data (e.g. AES)

## SSL Stripping 
- Definition: MITM - Attacker acts as a proxy and changes HTTPS to HTTP connections
- Getting to HTTPS:
  - Just typing in the domain we are interested in
  - Using a link from a search engine or that provided by another entity
- Process:
  - Request Sent to Web Server -> Actor Machine -> Web Server Receives it -> Web Server sends resources back to Client -> Recieved by Actor Machine that strips the resource of its SLL/TLS -> Client Receives Response back from Actor (Proxy/"Web Server") 
- Can be difficult to be in the MITM - it is not subtle attack
- Distant attackers would rather attack the client than attempt the more difficult MITM 
- If the attacker is on the network it is much easier to become the MITM
  - __ARP Spoofing__: tricking a client computer to thinking the machhine is the default gateway - ethernet does not have a method of authenticating (Address Resolution Protocol)
- Rogue Access Point: Fake Access Point that automatically strips the SSL from Responses
- Result:
  - The guarantees provided by TLS and SSL no longer exist so the data in transit can all be viewed in plain-text
    - Makes it easier to harvest passwords and other PII/confidential information
- Client Side Prevention:
  - Use an Encrypted Tunnel
    - SSH/VPN/Tunneling
  - Look at the provided URL
  - Use tools that monitor for ARP Spoofing/Poisoning
  - Network Isolation (VLANs)/Firewalls/Configurations on Wi-Fi

## HTTPS
- HTTP: Application Level Protocol 
  - Sends text to and from servers (plain-text)
- HTTPS: HTTP over TLS or SSL
  - Provides the guaranttes of TLS/SSL
  - Authentication/Integrity/Confidentiality
  - Process (Three-Way Handshake) - Establishing the Secure Channel:
    - Webserver starts tasks = Server send message to client indicating the start of a secure session
    - Client sends the security parameters that it requires
    - Server Compares those security paramters to those of its own
    - Server sends the digital certificate to the client
    - Client may be required to send a digital certificate to the server (Mutual Authentication)
      - Not frequent
      - Offers full authentication
    - If the client accepts the digital certification of the server the process continues
    - Client generates a symmetric session key (AES) and encrypts it with the server's public key and sends it to the server
    - This key is then used to transmit data back and forth between client and server
- Server Name Indication (SNI): Client identifies what host name they are attempting to connect to at the start of the handshake
  - Extension of TLS
    - Allows sever to present mutliple certificates on the same IP address and TCP port number and allow multiple secure HTTPs websites or any other service over TLS to be secured by the same IP Address without requires all sites using the same certificates
  - Ease Droppers can see what website you're accessing

## Digital Certificates
- Definition: authenticates a user and establishes a chain of trust - digital document about the owner of the certificate
  - public key and digitial key are validated by a certificate public authority
- X.509: standard that defines the format of public key certificates
- Fingerprints: Hash for the certificate
- Can find the subject's public key through the certificate
- __Chain of Trust__: The certificates that are issued that vouch for each other. Every operating has an established mutable list of root certificates that can be used 

## Certificate Authorities and HTTPS
- HTTPS relies on certificates for authentication
- Certificate ecosystem is vulnerable (e.g. Issuing a fake certificate)
  - Mistakes made by certificate authorities reduce the amount of "trust" in the ecosystem
  - Nation states can be certificate authorities
    - Issuing fake certificates giving this entity the ability to decrypt 
- Certificate authorities cannot be fully trusted
- Mitigation Methods:
  - Reduce the number of certificates that aren't necessary\
  - Watch for changes in the certificates that the system has (e.g. Certificate Patrol Add-On)
  - __Certificate Pinning__: process of assocaited a host with their expected public key/x509 certificate
  - Be Anonymous: Create attribution problem for those reading the content that is being decrypted
  - Use VPN: 
    - Only protects so much 

## End-to-End Encryption
- Definition: When the traffic/content is encrypted by the sender and only decrypted by the recipient
- E2EE + Zero Knowledge System: Cannot give any information to adversaries even if coerced 
- Offers protection in transit but not when received

## Steganography
- Definition: Concealing informaiton in files within other non-secret text
  - The data is just hidden NOT encrypt
  - If the file is fundamentally distroted or changed then the message will likely be lost (e.g. compression)
- Tools:
  - OpenPuff

## What Attackers go After
- Encryption works, thus attackers will seldom attempt to brute force an encryption password, especially when other means of attack could circumvent that
- Security is a __Weak Link Phenomena__: Only as strong as the weakest link in the chain
  - Encryption tends to be the strong link in the chain
  - People tend to be the weakest link in the chain
- Attackers only need to be lucky once to win - Defenders must be correct every time
  - Mitigate the weakest links (Greatest Risk) First

# OS Security & Privacy
## Virtual Machines (Platform Virtualization):
- Purpose:

### Type 1 (Bare Metal)
- Layers (Bottom -> Top):
  - Hardware
  - Hypervisor
  - Operating System

### Type 2 (Hosted)
- Layers (Bottom -> Top):
  - Hardware
  - Base Operating System
  - Hypervisor
  - Hosted Operating Systems(s) - Software that virtualizes (e.g. VirtualBox)

## Security Features and Functionality
- Operating System: manages computer hardware and software resources and provides common services for computer applications
  - Has full access to all part of the computing system
### Security Features
#### Windows
- Weak security design from the beginning -> improved over time
- has trackign and privacy issues

#### MacOs
- Solid base security
- Less third-party products available

#### Linux
- Has some of the most Security Focused Operating Systems

#### Android
- Open operating system

#### iOS
- Closed Operating System - Better for Security 

## Security Bugs and Vulnerabilities
- [CVE Details](https://cvedetails.com)
  - Can be used to understand the number of report Vulnerabilities for specific platforms (e.g. Operating systems, Applications, etc.)
- All operating system have serious critical security vulnerabilties
- There are occassionally issues with the reporting of vulnerabiltiies - could be reported as a singular vulnerability when in actually it is an amalgam of vulnerabilities
- The speed at which reported bugs and vulnerabilities are handled needs to be taken into consideration when decided on the OS used

## Usage Share
- The amount an usage Operating System has the greater the likelihood of there being people that would like to exploit that platform
- The highest market share will be attacked the most (especially those with the highest market share in places of critical infrastructure) 

## Windows - Potentially Outdated
### Windows 10
- Unsuitable for absolute privacy becasuse of the exterme about of telemetry data
  - Many cloud features
- Data Syncing: Privacy and application data are by default synced with microsoft
  - Can be diabled
- Advertising ID: Unique ID used for advertisers to personalize advertisements
  - Can be opted out of
- Cortana Data collection: Keystroke, Microphones, Emails, SMS, Music, Purchases, etc.
- Using Windows 10 requires that its users share their information with third-parties
  - Including: Name, Email, Address, Passowrds, Stocks, Cities, Age, Gender, Purchase, Browsing History, etc.
- There are tools available to minimize the tracking that Windows performs 
- Windows 10 (Major) updates tend to default the privacy/telemetry data back to the default values so it is imperative to reset those to your privacy posture/tolerance

### Windows 7, 8, 8.1
- Better than windows 10 for privacy
- Does send out telemetry data about performance of OS and microsoft applications

## Mac OS X - BSD derivative
- SPotlight search transmits the locations to Apple

## Linux and Unix-like Distribution
### Basing Operating System for Base Level Privacy
- Debian
- OpenBSD
- Arch Linux

## OS General Classifications
### General Use
- Windows
- MacOS 
- Linux (Ubuntu)

### General Use w/ Focus on Security and Privacy
- Debian
- Arch Linux

### Pure Security Focused 
- QubesOS
- Subgraph OS
- Trisquel OS

### Anonymity Focused
- Tails
- Whonix OS

### Mobile OS with Security and Privacy 
- LineageOS 
- Sailfish

# Security Bugs and Vulnerabilities

## Patching
- All software, applications, operating systems need to be patched
- THE MOST IMPORTANT THING to remain safe online
- Largest Attack Vectors:
  - Browser
  - Browser Extension and Plugins
  - Email Applications
  - Applications and other downloaded content
  - Operating System
- There is chance that the resulting update has a detrimental bug/vulnerability - know how to revert to previous versions
- Microsoft has tends to post patches on the second or fourth Tuesday of the month in North America
  - KB = Unique to the patch being installed
  - CVE = UNique to the vulnerability the patch is resolves
- Most applications, browsers, extensions, and operating systems provide a mechanism to auto update the software with the most recent patches/fixes
  - Auto-update does decrease the level of privacy and anonymity you possess
  - Updates can be malicious - if auto updated the auto update will serve as an attack vector to your machine

# Reducing Threat Privilege
- Upon exploiting a system/application most actors will have the level of access of the user they exploited (e.g. if the user has admin/root privileges then the assilant will have admin/root privileges)
- Restricting privilege can reduce the level access an exploitable system/application has and thus the level of privilege for the attacker
  - This further complicates the attacker's plan because they'll be forced to use privilege escalation techniques - exploits are not always available - which increases the attack surface
- It is particularly important in while on a Windows OS to avoid having admin privileges unless absolutely necessary

# Social Engineering and Social Media Offence and Defense

## Information Disclosure and Identity Strategies
- The less information out there the more easily anonymity and privacy can be attained
- The more information out in the public sphere the more easily adversaries can paint a picture of you
  - Need to minimize to reduce likelihood of profiling
- Many companies own the information that its users post on it
- Terms and Service Synopsis: [Terms](https://www.tosdr.org)
- Government Backing: [WhoHasBack](https://www.eff.org)
- There are decentralized social networks where there is not the expectation of using one's true identity
  
### Strategies (Precedence is in Desc Order)
1. Avoidance: Avoid using social media, not posting, not giving out information - recommended to use where possible
2. Compartmentalization: Revealing information about you but have all the social media account not attributable to you (creation of aliases)
3. Content: Only give out carefully considered information (need to be wary as to NEVER give out more information)
4. Audience: Keep personal and professional network separately (keeping things to separate platforms)
5. Open: Using transparent and authentic - makes you the most vulnerable and it bares the most risk
6. Custom: using a combination of the strategies

## Identify Verfication and Registration 
- Shared Accounts: [BugMeNot](bugmenot.com)
- Disposable Emails: [GuerillaMail](https://www.guerrillamail.com)

## Behavioural Security Controls Against Social Threats
### Behavioural Changes (Actions by People)
- If you didn't request don't click on it (e.g. random SMS/emails)
  - If you didn't expect it you should consider it suspicious
- Never download and run any file you don't 100%
  - All email attachments should be considered suspicious
- Never enter sensitive information after following a link or popup
- Validate the link (Watch out for link manipulation (e.g. IDN Homographic Attacks))
- Minimize personal information disclosure - lessens likelihood of being a target in an attack
- Validate with the Sender
- Validate the Attachment
  - Check For Known Malware: [VirusTotal](https://virustotal.com)
    - Virus total can be emailed Scan@virustotal.com
  - File Extension to be wary of:
    - .exe, .com, .vb, .vbs, .vbe, .cmd, .bat, .ws, .wsf, .scr, .shs, .pif, .hta, .js, .jse, .lnk, .deb, .rpm
  - Document Extension to be wary of:
    - .xls, .pdf, .docx, .doc
  - Compressed Files to be wary of:
    - .zip, .rar, .z, .Z, .7z, .DMG
- Watch out for SMSHING and Vishing

### Technical Security Controls 
- Many behavourial controls will also be mitigated with the use of the listed security controls
- Use email provided with security controls
  - Security and privacy can occur simultaneously
  - Want a provider to protect againt phishing
- Enabling the security notifications (e.g. on emails, banks, etc.)
- Use Google Safe Browsing
- Using VMs and Sandboxes
- Use OpenpGP signatures to validate senders
- Enable Endpoint protection

# Security Domains
- Security tends to make operations more cumbersome 
  - Impacts speed and usability
- Physical Security Domain
  - Example: Separation of information by using separate machines
- Virtual Security Domain
  - Example: Using Hypervisors to separate information through siloing of information

## Physical Security Domain
- Provides the highest level of security and privacy
- Includes: Disparate machines with varying levels of privacy and information access, Hiding the laptop or machine, new router
- Some physical equipment can be monetarily traced back to the purchaser 
- Can be expensive and slow, especially if you need to frequently transfer data between the machines, updating each of the machines, and using multiple at once

## Virtual Security Domain
- Provides a barrier to compromise
  - If the guest operating system is compromised then the compromiser would have to exploit the hypervisor as well - which tends not to happen
- Separate and Privacy Hard Drive Partitions
- Dual booting with Security and Privacy Specific Operating System 

# Security Through Isolation and Compartmentalization
## Intro Isolation and Compartmentalization
  - Most powerful security control
  - Used to implement security domains
  - Help to mitigate against the impact of exploitations
  - Assets should be isolated and compartmentalized

## Physical Security Isolation:
- Devices have hardware serial numbers that uniquely identify them
## Types:
### MAC Address:
- Always a unique number
- Like an IP address for the local address only
- The MAC could be traced back to a user
- The first 3 bytes are the manufacturer's ID
- The last 3 bytes are specific to the device -- unique to the device itself
- The MAC address needs to be changed if you wish to be anonymous
- Virtual Machines change the MAC address of the device
  - Static MACs should be changed every now and then
### CPU:
- Modern CPUs do not have software readable serial numbers
- CPUs can be examined with:
  - CPU-Z on windows
  - i-nex on linux
  - MacCPUID on MAC
### Motherboard:
- Typically have unique codes in the BIOS that could be tied back to a purchaser
- View:
  - Windows: from command prompt - wmic bios get name, serialnumber, version
             from command prompt - wmic csproduct ge name, identifyingnumber,uuid
  - Windows/MAC/Linux: dmidecode
### Hard Drives:
    - Have unique identifiers that could be tied back to the purchaser
### Mitigating Against Serial IDs:
- Using sophisticated tools to change the hardware codes of the physical devices
- Anonymously purchase the devices you purchase to prevent a money trail
- Use virtual machines for isolation and compartmentalization

## Virtual Isolation:
### Encryption and Compartmentalization:
- Separate data by its level of importance
  - Using difference encryption keys for each layer
  - Use hidden encryption levels to make them difficult to find
  - Setting up virtual remote server
### Dual Booting:
- Increasing security domains
- Reduces flexibility
- There is a privacy and security balance
- The systems could compromise each other
  - The file systems are not mutually exclusive
  - File sharing would need to be worked out
### Sandboxes: a container that protects the contents inside the container from spilling out
- Windows:
  - Bufferzone: Sandbox application
  - Shadow mode:
  - Sandboxie
### Portable Apps: self contained applications and do not require installation
- All changes are contained to a single file
- Benefits:
  - All the history of a browser would be located in a single file
  - Encrypting the application and its data would be easier because it is all in a single file
  - Admins rights are not necessary to run the portable applications
  - These applications can be run in the cloud
  - Applications as a software help with these

## Virtual Machines:
- Kind of sandbox
- Good tool for isolation and compartmentalization
- Virtualization reduces the interfaces between security domains
  - This virtualization makes it so they can communicate with each other (less devices)
- Type 1 Hypervisors: There is no host operating system
  - Hypervisor is the operating system
  - Tends to be more secure because there is no host
- Type 2 Hypervisors: Has a host operating system like virtualbox
### Virtual Machine Weaknesses:
- Key logging the host would weaken the guest
- Hardware compromises would weaken the guest
- Virtual machine can leak information through unwanted log files
  - basically showing the activities performed on the guest machine
- You don't know everything that is created on the host machine from the guest
### Virtual Machine Hardening:
- Physical Hardware:
  - Use a separate wifi adapter
  - Whole disk encryption to protect against virtual machine leaks
  - Have a hidden operating system where the whole disk is stored
  - Disable or delete caching
- General Hardening:
  - Enable Encryption for each of the virtual Machines
    - Only protects them while they are off
  - The encryption will slow down the machines
  - May want to disable audio and microphone
  - May want to cover webcam
  - Disable clipboard and drag and drop
  - Disable 3D acceleration
  - Avoid Guest additions if possible
  - Don't have shared files
  - Remove virtual disks if live operating system
  - Do not attach USB devices
    - Disable USB controller (off by default)
    - PS/2 Mouse is required if disable
  - Enable PAE/NX
    - Helps processor guard from malware
  - Remove anything that is not used
  - Use non-persistent operating systems
  - Do not add virtual storage when making the machine
  - Avoid sleeping/suspensions because the encryption keys will be stored on the hard disks
