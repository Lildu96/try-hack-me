# Pre Security
## Main Learning Points
- [Offensive and Defensive Security](#introduction-to-cyber-security)
- [Basics of Networking and the Web](#networking-fundamentals)
- [Basics of Linux and Windows](#linux-fundamentals)

## Introduction to Cyber Security
### Offensive Security (Red Teams)
- Breaking into systems/exploiting bugs/finding loopholes.
- Understand Tactics and enhance system defences.
#### Example Hack
Using a terminal use Gobuster to find hidden directories and pages.
Example command:
```
gobuster -u [site] -w [wordlist file] dir
```
- `-u` states the website
- `-w` states the wordlist being used to find hidden pages
I can now use any hidden pages found on the site in the browser to find exploits.

### Defensive Security (Blue Teams)
- Preventive measures to reduce incidents
- Detecting incidents and Respdoning accordingly
#### Defensive Security Tasks
- Training and awareness
- Knowledge of systems and devices to document and protect
- Updating and patching to keep devices secure
- Setting up Firewalls, IPS (intrusion prevention systems) which blocks network traffic matching rules and atttack signatures.
- Logging and Monitoring devices to detect incidents

## Networking Fundamentals
### What is Networking?
A Network is any connected devices</br>
The internet is a massive network connecting small networks. A repository to store and share information.</br>
The first iteration was within ARPNET project in the late 60s. Funded by the US Defence Department.</br>
It was invented in 1989 by Tim Berners-Lee (World Wide Web)</br>
Small networks are called Private Networks.</br>
Networks connecting private networks are public (the internet).</br>
#### Identifying Devices
There are two types of identification:
- IP Address (Internet Protocol)
- MAC Address (Media Access Control)
##### IP Addresses
Identifies a host on a network. Can be associated with another device and not change.</br>
They can change from one device to another but can't be active more than once, at the same time on the same network.</br>
They follow standards called protocols, forcing communication to be in the same language. Devices can have public or private IPs depending on where they are.</br>
A public IP identifies devices on the internet. A private IP identifies amongst other devices.</br>
Devices will have public and private IPs. Public IPs are given by the ISP (Internet Service Provider).</br>
Due to the amount of IP Addressed needed for the amount of devices being used in the world there are now versions:
- IPv4 - numbering systerm of 2^32 (4.29 billion)
- IPv6 - numbering system of 2^128(over 340 trillion)
An example IPv4:
```
192.168.1.2
```
- Octet #1 `192`
- Octet #2 `168`
- Octet #3 `1`
- Octet #4 `2`
All these numbers can be from 0-255.</br>
An exmple IPv6:
```
2a00:22ca:a531:c500:425f:cce6:c36b:f64d
```
##### MAC Addresses
The MAC is assigned by the factory to a physical network interface on the motherboard.
It's a twelve character hexdecimal numer (base sixteen numbering system to represent numbers in computing). They are split into two and have separators (colons). The first 6 chracters represent the company and the last 6 is a unique number. Example:
```
a4:c3:f0:85:ac:2d
```
These can be spoofed breaking poor security designs, assumes devices are trustworthy.</br>
Public places use MAC cotrol with guest or public wi-fi's. to exploit people for money in exchange for faster speeds.
#### Ping (ICMP(Internet Control Message Protocol)) 
Packets show the performance of a connection between devices. Ping is the measurement whic uses ICMP's echo packet and echo reply.</br>
Syntax:
```
ping [IP address/website URL]
```

### Intro to LAN
#### LAN Topologies
LAN (Local Area Network)</br>
Topology is the design of a network.
##### Star Topology
Devices are connected individually by a central networking device (switch or hub). This is reliable and scalable but costly.</br>
It is more expensive because of the cabling and equipment needed. The more it scales the more maintenance it needs. This can make troubleshooting hard. If the central device fails, connected devices can't send or receive data.
##### Bus Topology
A single connection known as a backbone cable. Like a tree where leaves are devices and the trunk is the backbone. Due to only one cable it can be slow and bottlenecked. Difficult to troubleshoot - don't know which device has issues. If the cable broke devices can no longer receive or send data.</br>
They are easier and cost efficent.
##### Ring Topology (Token)
Devices are connected directly to make a loop. Little cable is needed.</br>
A device only receives data if it doesn't have anything to send. If it does it sends it first before receiving.</br>
Only travels in one direction so easy to troubleshoot. Inefficent way to send data.</br>
They are less likely to get bottlenecked. A broken cable or device will stop the network working.
##### Switch
Aggregate multiple devices using ethernet. They can have ports of 4, 8, 16, 24, 32 and 64.</br>
Less efficent that hubs or repaters. It keeps track of where devices are plugged so it can send data to the intended target. - Reduces network traffic.</br>
Switches and router can be connect - Increases reliability by adding multiple paths. - Can reduce performance but no downtime.
##### Router
Connects networks and passes data by routing - Data travelling across networks by creatng a path. Devices can be connected by multiple paths.
#### Subnetting
Splitting a big network to smaller networks. Decide what gets which network. For example, different departments in a business. Accounting, Finance and HR. Admins categorise and assign parts of a network. By splitting up the number of hosts creating a subnet mask. Similar to an IP it is a number of four bytes or 32 bits ranging 0-255. Subnets use IPs to:
- Identify network address - Start of a network and existence. - An IP of 192.168.1.100 identfied by 192.168.1.0
- Identify host addrress - Identifies device on subnet - address: 192.168.1.1
- Identify default gateway - Address assigned to a device to sending information to another network - information that needs to go to a different network will be sent here. Can use any host address, normally first or last .1 or .254 (octet #4)
It is effiecient, secure and fully controlled.
#### ARP (Address Resolution Protocol)
How devices identify themselves by associating the MAC with the IP. Broadcast to the network searching for a device. ARP can find a MAC for communication.
##### How it works
Devices store info in caches. For ARP this is the identifiers. To map these it uses:
- ARP Request - Message of which mac uses this ip?
- ARP Reply - Respond if they own the ip with the mac.
This information is stored in the ARP cache.
#### DHCP (Dynamic Host Configuration Protocol)
If an IP address is not assigned manually it is does automatically using a DHCP server. Using this structure:
- DHCP Discover - Device searches for DHCP server
- DHCP Offer - Server replies with an IP
- DHCP Request - Devices confirms the offered IP
- DHCP ACK - Server acknowledges the confirmed offer

### OSi Model
#### OSI (Open Systems Interconnection)
a framework to dictate how devices send/receive/interpret data. Devices can have different functions and designs. Uniform data can be understood on the network. Consists of 7 layers. Goes 7-1. Pieces of information are added to the data called encapsulation:</br>
7. Application</br>
6. Presentation</br>
5. Session</br>
4. Transport</br>
3. Network</br>
2. Data Link</br>
1. Physical
#### Layer 1 - Physical
The physical components and hardware. Electrical signals are used to transfer data with binary.
#### Layer 2 - Data Link
Focuses on physical address of the transmission. Receives a packet from the network layer and adds the MAC of the endpoint. Presents the data suitable format for transmission.
#### Layer 3 - Network
Routing and data re-assembly. Some protocols determine exact optimal path - only know of their existance. Include protocols:
- OSPF (Open Shortest Path First)
- RIP (Routing Information Protocol)
Factors that decide route:
- Shortest path (least amount of devices)
- Reliable Path (previously lost packets?)
- Fastest connection ( copper or fibre?)
Everything uses IP addresses. Devices that deliver packets using IP's are layer 3 Devices.
#### Layer 4 - Transport
When data is sent between devices it follows one of two protocols:
- TCP (Transmission Contol Protocol
  - Reliable - constant connection for duration of data transfer. Inlcudes error checking. Guarantees data from Session Layer (5) is received and reassembled in the same order.
  - Guarantees accuracy - Requires reliable connection. If small chunk is not received, entire chunk is unusable.
  - Synchronises two devices to stop flooding of data - Can bottleneck another devices, connection reserved on receiving pc.
  - More processes for reliabality - Sower than UDP, more work needs doing by devices.
  - Used for file sharing, internet browsing, sending emails - They need to be accurate and complete.
- UDP (User Datagram Protocol)
  - Faster than TCP - does't care if data is received
  - uses software to control speed - Flexible to software developers
  - Does not reserve continuous conenction - unstable connection means bad user experience
  - Useful for small data - protocols used for discovery ( ARP and DHCP). Larger files like videa streaming (pixelated video)
#### Layer 5 - Session
Creates and maintains connection to other computer. Closes the connection if unused or lost. Can create checkpoints - only new data is required, saves bandwidth. Sessions are unique - data can't travel over different session.
#### Layer 6 - Presentation
Standardisation. Software developed different needs to be handled the same. Translates data to and from the application layer (7). Security features - data encryption (https) is at this layer.
#### Layer 7 - Application
How user interacts with data - GUI (Graphical User Interface) Protocols like DNS (Domain Name System) are sites translated to IPs

### Packets and Frames
#### What are they?
Small pieces of data - when combined create information or message.</br>
Frames are at the data link layer (2). The first envelope is the packet, the second enevelope is a frame. - Encapsulation.</br>
Anything to do with IP Addresses is to do with packets. when the encapsulated info is stripped - it's the frame.</br>
Packets communicate data across networks. They have different structures depending on the packet sent.</br>
Standards and protocols means things don't break.
#### TCP/IP (Three-Way Handshake)
(Transmissiong Control Protocol)</br>
Similar to OSI Model with 4 layers:
- Application
- Transport
- Internet
- Network Interface <br/>

Information is added to each layer as a packet travels. - Encapsulation, reverse is decapsulation.</br>
TCP is conenction-based - a connection between client and device (server) needs to be established. - Guarantees data is sent. - Three-way handshake.
</br>

Advantages:
- Guarantees integrity of data
- Sync 2 devces to prevent flooding of data.
- Performs more process reliably
<br/>

Disadvantages:  
- Requires a reliable connecting. Data unsuable if something is missed.
- Slow connectiong can bottleneck - connection is reserved on other devices.
- Slower - more computing needs doing.
<br/>

TCP packets contains sections - headers. Crucial headers:
- Source Port - Port opened by the sender, value is chosen randomly (0-65535)
- Destination Port - Port that an app or service is running on remote (receiving). This is not randomly chosen
- Source IP - IP of sender
- Destination IP - IP of receiver
- Sequence Numer - First piece of data is given a random number.
- Acknowledgement number - Sequence number +1
- Checksum - TCP integrity. A calcuation to remember the output. If the calculation is different between receiving and sending it is corrupt
- Data - Bytes are stored
- Flag - How the packet is handled. Flags have different behaviours.
</br>

The Three-Way Handshake communicates with messages:
- Step 1 - SYN - Initial packet - creates connection and sync devices.
- Step 2 - SYN/ACK - Packet sent by receiving device - acknowledge sync
- Step 3 - ACK - Acknowledges messages/packets are received
- Step 4 - DATA - Data is sent
- Step 5 - FIN - Cleanly closes the connection
- Step # - RST - Ends all communication, a last resort and a problem during.
</br>

Sent data is given a random number which incriments by 1. Both devices agree on the same sequence. Three steps:
1. SYN - Client: Here's my Initial Sequence Number(ISN) to SYNchronise with (0)
2. SYN/ACK - Server: Here's my Initial Sequence Number (ISN) to SYNchronise with (5,000), and I ACKnowledge your initial number sequence (0)
3. ACK - Client: I ACKnowledge your Initial Sequence Number (ISN) of (5,000), here is some data that is my ISN+1 (0 + 1)</br>

A connection is closed when the devices confirm all the dtaa has been received. Best practice to close asap. FIN packet is sent - then acknowledged.

#### UDP/IP
User Datagram Protocol</br>
A statless protocol- doesn't require a constant connection. Can tolerate data being lost. No safeguards Advantages:
- Faster
- Application decides speed of packets.
- no continuous connection
Disadvantages:
- Missing data
- Flexible to devs
- bad experience
Standard headers across protocols:
- Time to Live (TTL) - Expiry for packet, doesn't clog network.
- Source Address - IP of sent packet, can return here
- Destination Address - IP of recieinv device, where to travel
- Source Port - port opened by sender, randomly chosen (0-65535)
- Destination Port - Port that an app or service is running on remote (receiving). This is not randomly chosen
- Data - bytes are stored
Communication:
- Request  <--
- Response -->
- Response -->
- Response -->

#### Ports 101
Ports are point where data can be exchanged. Ports enforce what can go where. When a connection is established data is sent through ports. A numerical value between 0 and 65535. Standards to organise ports. Ports within 0 and 1024 are common ports:
- FTP - 21 - file sharing application, client/server model, download from central location.
- SSH - 22 - Securely login to systems, text-based interface
- HTTP - 80 - WWW, browsers
- HTTPS - 443 - Secure, encrypted
- SMB - 445 - similar to FTP, share devices
- RDP - 3389 - Log into a system wth a visual desktop interface.
[more](https://www.vmaxx.net/techinfo/ports.htm)</br>
Can administer applications ith different port numbers - need to be specifided with :

### Extending your Network
#### Introduction to Port Forwarding
Connects app and services to the internet by opening specific ports at the router. If not connecting they're only available to device on the same network. (Intranet)
Can confuse Port FOrwarding with the firewall. Firewalls determine what traffic can cross the ports.

#### Firewals 101
Firewall determines what can enter and exit. Examples of configuration:
- Where the traffic comes from
- where it's going
- Which port?
- Which protocol?
Answers are determined by packet inspection.</br>
They can be hardware (large networks) or Software. There are 2 to 5 categories. The two maine ones:
- Stateful
   - Entire information from connection instead of individual packets. Determines behaviour of device.
   - Consumes resources, decision making is dynamic. Can allow first part of TCP handshake but later fail.
   - If connection is bad, blocks entire device
- Stateless
  - Static rules to allow indiviual packets.
  - Use fewer resources but dumber. Only effective as the rules defined.
  - Great for large amounts (Distributed Denial-of-Servicve attck)

#### VPN Basics
Virtual Private Network (VPN) creates a dedicated path on ther internet (a tunnel) for devices to communication on a private network.</br>
Benefits:
- Allows networks in different locations to connect - A business with multiple offices.
- Privacy - Encrypted, only for destined devices sending and receiving, no sniffing. Useful in public wifi
- Anonymity - Report global issues where freedom of speech is controlled. Usually viwed by ISP and tracked. A VPN that logs data/history is not worth.
VPN Technologies:
- PPP - used by PPTP to allow auth and encryption. Work using a private key and public cert, they must match. It's not routable
- PPTP - Point-to-Point Tunneling Protocol Technology allows PPP to travel and leave. Easy set-up and most supported. Weak encryption.
- IPSec - Internet Protocol Security encrypts using IP framework. Difficult to set up. Strong encryption and mostly supported.

#### LAN Networking Devices
##### What is a Router?
Routers connect networks and pass data by routing. Creates a path. Operate at Layer 3 (Network). Can have interface (website or console) for admin configs like port forwarding and firewalls. They are not the same as switches. Routing chosen by different factors:
- Which protocol
- Shortest path
- Reliable path
- Faster medium (copper/fibre)
##### What is a Switch
Connects multiple devices (3- 63) with ethernet cables. Operate at Layer 2 (Data Link) and Layer 3 (Netowrk). Layer 2 switch doesn't work on Layer 3 switch. Layer 2 forwards frames using MAC address. Layer 3 can be same as router. Can send frames and route packets.</br>
VLAN (Virtual Local Area Network) allows specific devices to be virtually split up. Can beneift an internet connection but treated separately. This provides security using rules to say ow devices communicate.

## How The Web Works
### DNS in Detail
DNS (Domain Name System) is a way to communicate on the internet without complex numbers. Instead of remember IP Addresses we remember website names.
#### Domain Hierarchy
##### TLD (Top-Level Domain)
Righthand part of a domain name. .com/.co.uk etc.</br>
Two types:
- gTLD (Generic Top Level Domain) - Domain name purpose - .org = organisation
- ccTLD (Country Code Top Level Domain) - Geopgraphical - .co.uk = UK
Due to demand there is new gTLDs (over 2000)

##### Second-Level Domain
The name of the website is the Second Level (github). Limited to 63 char's. Can't use special characters apart from hyphens. Can't start or end with or have executive hyphens.

##### Subdomain
On left hand side of the Second-evel. Same creation restrictions as the Second-Level. Multiple subdomains can be used - length must be 253 char's or less. No limit of subdomains

#### Record Types
Not just for Websites:
- A Record - resolve to IPv4
- AAAA Record - resolve IPv6
- CNAME Record - resolve to another domain name. an online store can return a CNAME record to shopify for example. Another request would be used to work out the IP.
- MX Record - resolve to server address which handles the email for the domain. Come with a priority flag - which order to try the servers. If main server goes down an email can be sent to a backup.
- TXT Record - Free text fields to store text based data. Uses include:
  - list authoritive servers to send emails, helps against spam and spoof.
  - Verify ownership when signing up to third parties.

#### Making a Request
What Happens?
1. Pc checks cache if recently searched. Otherwise a request to Recursive DS Server is made.
2. A recursive DNS Server is provided by your ISP but can be chosen. Has a local cache. Request ends if it is found locally. If not it starts at the root DNS servers.
3. The root servers are the DNS backbone. They redirect you to the Top Level Domain. If it is .com it is recognised and sent to the correct TLD server.
4. TLD server holds record for the authoritive server or nameserver. Multiple nameservers as backups.
5. An Authoritive DNS server store the DNS records. Domain names and updates to domain names. DNS record is sent back to the Recursicve DNS Server - copy is cached for future. They have a TTL value - a number in seconds for length of save time. Caching saves on making requests.

### HTTP in Detail
#### What is it?
HyperText Transfer Protocol (HTTP) is used to view a site. Developed by Tim Berners-Lee between 1989-1991. Rules for communcating with web server to transmit webpage data.</br>
HTTPS (Secure) is secure. Stops people seeing sent and received data. Not talking to an impersonated web server.

#### Requests and Responses
Browser makes requests to server for parts of the site. It is told where to go by URLs (Uniform Resource Locator).
##### What is a URL?
An instruction to access a resource. Features of a URL, from left to right:
- Scheme - Which protocol to use to access HTTP, HTTPS, FTP etc.
- User - Authentication. Username and password can be put into url
- Host/Domain - Domain name or IP of server to access
- Port - Port for connection. Normally 80 for HTTP and 443 for HTTPS. Can be between 1 - 65535
- Path - File name of location
- Query String - Information to access specific parts of the website
- Fragment - Reference to a location on the requsted page. Used for long content and links to direct part of the page.
##### Making a Request
Can make a request with GET / HTTP/1.1 </br>
For better wbe experience headers are sent with more data and information to the server. Example:
```
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com

```
Line 1: Sending GET method to reuqest homepage with / and using HTTP v1.1  
Line 2: Which website we want 
Line 3: Which browser and version  
Line 4: Referred page  
Line 5: End with a blank line to finish the request.  
Example Response:
```
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
  <title>TryHackMe</title>
</head>
<body>
  Welcome to TryHackMe.com
</body>
</html>
```
Line 1: HTTP server and status code - successful  
Line 2: Server software and version  
Line 3: Date/time/timezone  
Line 4: Which type of information is sent  
Line 5: Length of Response - confirm no missing data  
Line 6: Blank Line confirms end of response
Line 7-14: Information requested
