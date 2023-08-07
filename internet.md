- [How Does the Internet Work (General)](#how-does-the-internet-work-general)
  - [What is the Internet](#what-is-the-internet)
    - [Who Uses the Internet](#who-uses-the-internet)
      - [Normal People](#normal-people)
      - [Business Entities](#business-entities)
      - [Academics:](#academics)
      - [Governments:](#governments)
      - [Cyber Criminals:](#cyber-criminals)
    - [How is the Internet Accessed](#how-is-the-internet-accessed)
    - [Advantages and Disadvantages of the Internet](#advantages-and-disadvantages-of-the-internet)
      - [Advantages of Internet](#advantages-of-internet)
      - [Disadvantages of Internet](#disadvantages-of-internet)
    - [Who Maitains the Internet](#who-maitains-the-internet)
      - [Internet Technology Standards](#internet-technology-standards)
      - [Domain Names and IP Addresses](#domain-names-and-ip-addresses)
        - [Regional Internet Registries](#regional-internet-registries)
      - [World Wide Web](#world-wide-web)
      - [Internet Infrastructure](#internet-infrastructure)
  - [Makes Internet Possible and What Exists on it](#makes-internet-possible-and-what-exists-on-it)
    - [Networking](#networking)
      - [Hardware](#hardware)
        - [Cable](#cable)
        - [Router](#router)
          - [Router Functions](#router-functions)
        - [Switch (DataLink Layer)](#switch-datalink-layer)
          - [Switch Options](#switch-options)
        - [Hub (Physical Layer)](#hub-physical-layer)
        - [Wireless Access Point (WAP)](#wireless-access-point-wap)
        - [DNS Servers](#dns-servers)
          - [Types of DNS Queries](#types-of-dns-queries)
          - [Types of DNS Records](#types-of-dns-records)
          - [Types of Caching](#types-of-caching)
      - [Computer Communication Models](#computer-communication-models)
        - [OSI (Open Systems Interconection) Model](#osi-open-systems-interconection-model)
          - [Bottom Layer - Layer 1: Physical - Media Layer](#bottom-layer---layer-1-physical---media-layer)
          - [Layer 2: Datalink - Media Layer](#layer-2-datalink---media-layer)
          - [Layer 3: Network - Media Layer](#layer-3-network---media-layer)
          - [Layer 4: Transport - Host Layer](#layer-4-transport---host-layer)
          - [Layer 5: Session - Host Layer](#layer-5-session---host-layer)
          - [Layer 6: Presentation - Host Layer](#layer-6-presentation---host-layer)
          - [Top Layer - Layer 7: Application - Host Layer](#top-layer---layer-7-application---host-layer)
          - [Explicit Transportation Process:](#explicit-transportation-process)
        - [TCP/IP Model](#tcpip-model)
          - [Top Layer 1: Application](#top-layer-1-application)
          - [Layer 2: Transport](#layer-2-transport)
          - [Layer 3: Network Access](#layer-3-network-access)
          - [Layer 4: Network Interface](#layer-4-network-interface)
          - [Layer 5: Hardware](#layer-5-hardware)
      - [Types and Topology of Networks](#types-and-topology-of-networks)
      - [Computer Network Architectures](#computer-network-architectures)
      - [Virtual Networks](#virtual-networks)
    - [The Cloud](#the-cloud)
      - [SaaS (Software as a Service)](#saas-software-as-a-service)
      - [PasS (Platform as a Service)](#pass-platform-as-a-service)
      - [IaaS (Infrastructure as a Service)](#iaas-infrastructure-as-a-service)
      - [DMaaS (Data Management as a Service)](#dmaas-data-management-as-a-service)
- [Glossary](#glossary)


# How Does the Internet Work (General)
## What is the Internet
- The Internet is exactly as the name suggest a network of networks that communicate between each other using the IP (Internet Protocol) suite. The Internet is a scoped globally and allows for the transferrence of information, resources, and entertainment through the use of services and standardized protocols.

### Who Uses the Internet
#### Normal People
- Using an Internet browser to access Netflix, Wikipedia, GitHub, Amazon, Etc.
- Play multiplayer online games with their friends
- Monitor their estates with internet connected devices (e.g. Amazon's Ring)

#### Business Entities
- Partition their intranet to allow Internet users to access files on their webserver
- Communicate between business entities with online audio and web conferencing platforms
- Collaboratively write and edit documentation with SaaS products

#### Academics:
- Access centrally-held research clusters to process large-scale datasets
- Host webservers to access white papers and other publications
- General Research

#### Governments:
- OSINT (Open-Source Intelligence)
- Survey the economic, political, and social climate other other regions and regimes 
- Communicate between other governmental agencies to coordinate action (e.g. EPA communicating with local government after rail derailings)

#### Cyber Criminals:
- OSINT: using freely available information to create a profile on their target
- Exchange/Trade illicit goods and services
- Create private forums to speak with other cyber criminals

### How is the Internet Accessed
- The typical procedures of accessing the internet is through an ISP (Internet-Service Provider) that serve the region where Internet is desired. Internet is accessible through many forms:
  - __Dial-Up__: communication established between modems by dialing a phone number on a telephone line 
    - Data transmitted from the sending modem would be modulated from digital to analog through the conventional telephone line to another modem that would demodualte it from analog to digital for the receiving computer to process 
    - Phones could not be used at the same time during the "Internet Call"
    - Download Speed: Approximate Maximum of 56 Kbps (Kilobits per second)
  - __DSL__ (Digital Subscriber Line): Like dial-up, DSL provided a means of communicating over a telephone line
    - Solved the problem non-simultaneous voice and internet over telephone line (allowed concurrent audio and internet use)
    - Download Speed: 12-25 Mbps (Megabits per second)
  - __Cable__: internet that is provided over coaxial cables (same cables as television)
    - Operates similarly to DSLs, in that existing infrastructure is leveraged to simultaneously provide internet and another service
      - Download Speed: Approximate Average 80Mbps
  - __Fiber__: Pulses of light that is transmitted through fiber optic cables - size required to transmit the data is so small that cables are bundled together in trunk cables (have multiple fiber lines) 
    - Form the backbone of the internet by connecting IXPs (Internet Exchange Points) together
    - Utilizes DWDM (Dense Wavelength-Divison Wavelength)
    - Download Speed: 300Mbps - 1Gbps+
  - __Satellite__: A form of wireless internet beamed down from satellites that orbit the Earth
    - Latency is the biggest concern with satellite
    - Download Speeds: Variable 
  - __Wireless__ (3G, 4G, 5G):
    - 3G: 3rd-Generation
    - 4G: 4th-Generation
      - LTE: Long Term Evolution
    - 5G: 5th-Generation 
  
### Advantages and Disadvantages of the Internet
#### Advantages of Internet
- People across the world can communicate - creates spaces where otherwise estranged people can convene and ideate
- Provide access to resources that would otherwise be inaccessible
- Facilitate 
- Refactor of translocating - GPS (e.g. Google Maps, Apple Maps)

#### Disadvantages of Internet
- Continuous innovation increases capabilities of services available but contributes to the digital divide
- People across the world can communicate
  - Bad actors need not be in a centralized location to cooperate
- Accelerate misinformation problem
- Activity and communications can be obsfucated/anonymized/privatized:
  - Encryption
  - Steganography
  - Tor
  - VPN (Virtual Private Network)
  - VPS (Virtual Private Server)


### Who Maitains the Internet
#### Internet Technology Standards
- ISOC (Internet Society):
- IAB (Internet Architecture Board):
- IESG (Internet Engineering Group):
- IETF (Internet Engineering Steering Group):
- IRSG (Internet Research Steering Group):
- IRTF (Internet Research Task Force):
- RFC Editor:
  
#### Domain Names and IP Addresses
- ICANN (Internet Corporation for Assigned Names and Numbers)
- IANA (Internet Assigned Numbers Authority)

##### Regional Internet Registries
- AfriNIC (African Network Information Centre)
- ARIN (American Registry for Internet Numbers)
- APNIC (Asia-Pacific Network Information Centre)
- LACNIC (Latin America and Caribbean Network Information Centre)
- RIPE (Réseaux IP Européens Network Coordination Centre):

#### World Wide Web
- World Wide Web Consortium

#### Internet Infrastructure
- ISPs (Internet Service Providers):
  - Tier 1: large providers that own operate, and maintain internet infrastructure and backbone (e.g. Verison, Zayo)
  - Tier 2: practice peering with other networks and purchase IP transit to reach other portions of the Internet
    - Most Common
  - Tier 3: Last-mile service - internet providers providing internet to residents 
    - Near solely purchases IP transit from other networks
- IXPs (Internet Exchange Points):

## Makes Internet Possible and What Exists on it 


### Networking
#### Hardware
##### Cable
- Purpose: Carry signals
- Coaxial Cables: standard of 10 Mbps Ethernet cables
  - Stiffness of thinnet and thicknet cables made maintainence difficult
- Twisted Pair Cables: 10 Mbps Ethernet (Cat 3) to 100 Mbps Ethernet (Cat 5(e)), up to 10 Gbps
  - 8 wires wound together to minimize electromagnetic interference
  - __Types__: Unshielded Twisted Pair and Shielded Twisted Pair
- Fiber Optics Cables: strands of glass and pulses of light 
  - Particularly useful in WANs
  - Types: Single-Mode (100BaseBX standard) and Multimode (100BaseSX standard)
    - Single-mode tends towards higher bandwidth
- USB (Universal Serial Bus) Cables: connect computer with peripheral device (use twisted-pair wiring)
  - Dongle: connect Ethernet cable to USB port indirectly

##### Router
- Purpose: Connect computers and other devices, allowing them to speak with each other while analyzing data that traverses across them
- __Wired Router__: share data over cables and create local area networks (LANs)
- __Wireless Router__: share data wireless and create wireless local area networks (WLANs)
- __Edge Router__: wired or wireless router that distributes data packets between one or mroe networks but not within a network 
  - Placed at the edge or boundary of networks (e.g. connecting to ISPs or other organizations networks)
  - Purpose: keep owning networking communicating with other networks 
- __Core Router__: wire or wireless network distribute data packets within networks, but not between networks 
  - Purpose: do the majority of data transferring 
- __Virtual Router__: software that allow computers and servers to operate like routers 
  - Can offer more flexibility than physical devices (e.g. can scale as necessary)

###### Router Functions
- Forwarding: Check packet headers and checksums, look for appropriate port based on routing table and then forwards to port
- Routing: determining the best path for the packet to reach the destination 
- Network Address Translation (NAT): translations between different IP address ranges 
  - Allows devices on a private network to access the internet using a single public IP address
- Security: can be configured with firewalls
- Quality of Service: can prioritize network traffic based on the type of data being transmitted
- Virtual Private Network (VPN) connectivity: Can be configured to allow remote users to connect securely to the network

##### Switch (DataLink Layer)
- Purpose: connect devices within a network and forward data packets to and from those device (only sends data to the device it is intended for) and can filter data (filter = identify the destination of the packet with routing table)
- __Modular Switch__: allow for the addition of expansion modules as needed
  - Expansion Module Examples: Firewalls, Wireless Connectivity, Power Supplies, Cooling Fans
  - Increased flexibility
- __Fixed Configuration Switch__: fixed number of ports and are not typically expandable
  - __Unmanaged Switch__: provide basic connectivity with no necesssary configuration 
  - __Smart Switch__: offer some management and segmentation, quality fo service and security capabiltiies
    - Deployed at edges of networks
  - __Managed Switch__: best application experience, highest level of security, more precise control and management of the network, greatest scalability
    - Deployed as aggregation/access switches in very large network or core switches in smaller networks 
  
###### Switch Options
- Switch Speeds: defines the throughput (rate data is transmitted) speed the switch is capable of  
- Number of Ports: defines the number of devices that can be physically attached to the switch 
- Power-Over-Eternet (PoE): power devices with ethernet 
- Stacking Capabilities: defines whether the switch can be connected with other switch to increase the network capacity 
  - Consider for redundancy

##### Hub (Physical Layer)
- Purpose: Used to connect multiple devices in a network - possessing multiple ports, unlike a switch the ports are non-intelligent and cannot indentify the destination of the port so the packet is broadcasted over all ports with a connected device
- __Active Hub__: possess power supply for regenerating weak signals and then sends signal to all ports
- __Passive Hub__: used to connect signals from different network cables (no computerized element)
  - Do not process or perform signal regeneration 
- __Intelligent Hub__: performs similar work as active hubs but possesses a monitoring unit - Management Information Base(MIB)
  - Management Information Base: helps in analyzing and troubleshooting network problem 

##### Wireless Access Point (WAP)
- Purpose: allows wireless-capable devices to connect to a wired network
  - Can also be used to extend the signal range and strength of your wireless network to provide complete wireless coverage
- __Root Access Point__: access point is connected directly to a wired LAN, providing a connection point for wireless users
- __Repeater Access Point__: extends the range of existing infrastructure or overcome an obstacle that blocks radio communication 
  - Forwards traffic between wiresless users and the wired network by sending data to either another repeater or an access point that is connected to the wire network 
- __Bridge__: establishes a wireless link with a non-root bridge and traffic is passed over the wireless link to the wired network
- __Workgroup Bridge__: access points in a workgroup can associate to other access points as clients and provide network connections for devices connected to Ethernet ports
- __Central Unit in an **All-Wireless Network**__: access point acts as a hub that links all stations together - focal point for communication

##### [DNS Servers](https://www.cloudflare.com/learning/dns/what-is-dns/)
- Purpose: 
- __Recursive Resolver__: intemediary between client and DNS nameserver and the first stop in a DNS query 
  - Process:
    - Receives DNS Query from Client
    - Checks Cached Data
      - If requested data is has been cached the recursive resolver will send that data to the client
      - If request data has NOT been cached the recursive resolver will send a request to a root nameserver, then TLD nameserver and lastly to an authoritative nameserver
    - After receiving the response from the authoritative namesever the recursive resolver sends the response to the client and caches it for future queries
  - Alternate Process
    - If resolver has NS records for authoritative nameserver they are queried directly (bypasses lookups to root and TLD servers)
    - If resolver does not have NS records it will query TLD servers and skips the root server
    - IF resolver does not have records for TLD server the root servers are queried (typically occurring after a cache purge)
- __Root Nameserver__: accepts queries from recursive resolvers, which includes a domain name
  - Process:
    - Root Nameserver receives request from recursive resolver
    - Root Nameserver responds with directions to a TLD Nameserver based on the domain extension (e.g. .com, .net) 
  - 13 types of rootname servers
  - Use Anycast Routing
- __TLD Nameserver__: maintains information for all domain names that share a common domain extension
  - Process: 
    - Receive query from recursive resolver
    - TLD Nameserver responds with direction to an Authoritative Nameserver
  - Generic TLDs: .com, .org, .net, .edu, .gov
  - Country Code TLDs: .uk, .us, .ru, .jp
- __Authoritative Nameserver__: contains information specific to the domain name it serves and can provide the recursive resolver with the IP address of that server found in the DNS A record or a CNAME record (can satify queries without needing to query another source for non-subdomains)
  - Process:
    - Authoritative Nameserver receives query from recursive resolver
    - Authoritative Nameserver responds:
      - Responds with A Record: contains the IP address
      - Responds with CNAME Record:
        - Provides the recursive resolver with an alias domain
        - Recursive resolver performs a whole new DNS lookup with the alias

###### Types of DNS Queries
- __Recursive__: client requires that a DNS server will respond to the client with either the requested resource record or an error message if the resolver can't find the record
- __Iterative__: client will allow the server to return the best answer it can 
  - If no match: server returns a referral to an authoritative server for a lower level of the domain namespace - client will then make a query to the referral address - process continues until either error or timeout 
- __Non-Recursive__: client queries a server for a record that is has access to either because it's authoritative for the record or the record exists inside of its cache  

###### Types of DNS Records
- __A (Address) Record__: most fundamental DNS Record, primarily used for matching a domain name to an IPv4 address - enables a user's device to connect with and load a website, without the user memorizing and typing in the actual IP address 
  - Contains only IPv4 address
- __AAAA Record__: enable client devices to learn the IP address for a domain name
  - Contains only IPv6 
- __CNAME Record__: used in lieu of an A record, when a domain or subdomain is an alias of another domain - points from an alias domain to a "canonical" domain
  - Must point to a domain NOT an IP address
  - Frequently used for subdomains
  - Does NOT have to resolve to the same website as the domain it points to
    - Must only point to the same IP address as the root domain
    - The webserver will handle the URL accordingly which could point to an entire differnet file on the webserver
  - CNAME records can point to other CNAME records - requires multiple DNS lookups 
- __MX Record__: directs emails to a mail server - indicates how email messages should be routed relative to SMTP (Simple Mail Transport Protocol)
  - Have an order of precedence - lower value = more
  - Cannot point to CNAME - must point to A or AAAA record
- __TXT Record__: [TXT-Record](https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/)
- __NS (Nameserver) Record__: indicates which DNS server is authortiative for a specific domain, which tells the internet where to go to find a domain's IP
  - Never point to a CNMAE
  - Domain can have multiple NS records which can indicate priamry and secondary nameservers
    - Nameserver: stores all DNS records for a domain 
    - Multiple nameservers increase network reliability (typically one primary and multiple nameserver - updating primary nameserver will trigger an update of secondary nameservers)
- __SOA (Start of Authority) Record__: stores information about a domain or zone (e.g. email of admin, when domain was updated last, how long the server shoudl wait between refreshes)
  - zone = area of control over namespace 
  - Parts of SOA Record:
    - MNAME: name of primary nameserver for the zone
    - REFRESH: length of time secondary servers should wait before asking primary servers for the SOA record to see if it has been updated
    - RETRY: length of time a server should wait for asking an unresponsive primary nameserver for an update again
    - EXPIRE: if a secondary server does not get a response from the primary server for this amount of time, it should stop responding to queries for the zone
- __SRV (Service) Record__: specifies a host and port for specific services 
  - SRV Record Contains:
    - Transmission Protocol used
    - Priority: prioritization of one server over another - the lower the value the more traffic
    - Weight: priorization of one server over another with the same priority value
- __PTR Record__: correlates domain names with IP address (opposite of the A reocrd)
  - Used for reverse DNS lookups: query starts with the IP address and looks up the domain name
- __KEY and DS Records__:
  - __DNSSEC__: optional security protocol - adds cryptographic signatures to DNS records that can be checked to verify that a record came from the correct DNS server
    - KEY Record: public signing key *private key is not on record
    - DS Record: hash of KEY record
- __SPF (Sender Policy Framework) Record__: lists all the servers authorized to send emails from a particular domain  
- __DKIM (DomainKeys Identified Mail) Record__: method of email authentication that helps prevent spammers and other malicious parties from impersonating a legitmate domain
- __DMARC (Domain-based Message Authentication Reporting and Conformance) Record__: method of authenticating email messages - tells a reciving email server what to do after checking a domain's SPF and DKIM - prevent email spoofing

###### Types of Caching
- __Browser DNS__: the closer the DNS caching occurs to the web browser, the fewer processing steps must be taken in order to check the cache and make the correct requests to an IP
  - First location checked for DNS querys
- __Operating System DNS__ (referred to as stub resovler): checks its own cache to see if ti has the record - if it does not then it sends a DNS query (with recursive flag set) outside of the local network
  - Second stop for DNS query before request leaves machine

#### Computer Communication Models
- Computer Communication Models serve to standardize the coordination of communication between networked computing systems

##### OSI (Open Systems Interconection) Model
- Each layer in the model have well-defined functions, and the methods of each layer communicate and interact with those adjacent to it (when necesary)

###### Bottom Layer - Layer 1: Physical - Media Layer
###### Layer 2: Datalink - Media Layer
###### Layer 3: Network - Media Layer
###### Layer 4: Transport - Host Layer
###### Layer 5: Session - Host Layer
###### Layer 6: Presentation - Host Layer
###### Top Layer - Layer 7: Application - Host Layer

###### Explicit Transportation Process:
  1. The data that is intended to be transmitted is composed at the topmost layer (Application Layer) into a PDU (Protocol Data Unit)
  2. The PDU is passed to the next layer (Presentation Layer) where it is referred to as a SDU (Service Data Unit)
  3. The SDU at the presentation layer is "serviced" and is concatenated with a header, a footer, or both. The concatenation of the header and footer turn the SDU into a Presentation Layer PDU and is then transmitted to the Session Layer.
  4. The Presentation Layer PDU is referred to as an SDU in the Session layer, where it is "serviced" and is now referred to as a Session PDU and is transmitted to the Transport Layer.
  5. The Session Layer PDU is now referred to as an SDU in the Transport layer, where it is "service" and is now referred to as a Transport Layer PDU and is then transmitted to the Network Layer
  6. The Transport Layer PDU is now referred to as an SDU in the Network Layer, where it is "serviced" and is now referred to as a Network Layer PDU and is then transmitted to the Datalink Layer
  7. The Network Layer PDU is now referred to as an SDU in the Datalink layer, where it is "serviced" as is now referred to as a Datalink layer PDU and is then transmitted to the Physical Layer
  8. The Datalink PDU is now referred to as an SDU in the Physical Layer, where it is "serviced" and transmitted to the receiving device
  9. The receiving device receives the transmitting machine's Physical Layer PDU
  10. The receiving device's Physical Layer strips the transmitting device's Physical Layer PDU of its "serviced" headers and footers, which at the point of reception is referred to as an SDU
  11. The received SDU is passed from the bottom layer back to the top on the receiving device and at each layer the associated "serviced" headers and footers from the transmitting device are stripped, until the application layer, at which point the data can be consumed

##### TCP/IP Model
###### Top Layer 1: Application
###### Layer 2: Transport 
###### Layer 3: Network Access
###### Layer 4: Network Interface
###### Layer 5: Hardware  
 

#### Types and Topology of Networks

#### Computer Network Architectures
- Client-Server
- P2P (Peer-to-Peer)
#### Virtual Networks


### The Cloud
#### SaaS (Software as a Service)
#### PasS (Platform as a Service)
#### IaaS (Infrastructure as a Service)
#### DMaaS (Data Management as a Service)



# Glossary
- Protocol: 
- Internet Protocol:
- Protocol Suite:
- Internet Browser:
- Internet of Things:
- Intranet:
- Webserver:
- Firewall:
- SaaS
- The Cloud:
- Internet Service Provider:
- Digitl 
- Analog
- Internet Exchange Points:
- Dense Wavelength-Division Wavelength: 
- Digital Divide: 
- Privacy:
- Anonymity: 
- Regional Internet Registries:
- IP transit:
- Peering: 
- Private Peering: 
- Protocol Data Unit: 
- Service Data Unit: