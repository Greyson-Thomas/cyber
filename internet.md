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
- ISOC (Internet SOciety):
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