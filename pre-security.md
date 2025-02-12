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
A single connectection known as a backbone cable. Like a tree where leaves are devices and the trunk is the backbone. Due to only one cable it can be slow and bottlenecked. Difficult to troubleshoot - don't know which device has issues. If the cable broke devices can no longer receive or send data.</br>
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
