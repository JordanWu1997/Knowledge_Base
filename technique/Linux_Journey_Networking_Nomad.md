# Linux Journey - Networking Nomad
- Reference
    - https://linuxjourney.com/lesson/network-file-sharing
    - https://linuxjourney.com/lesson/network-basics
    - https://linuxjourney.com/lesson/ipv4
    - https://en.wikipedia.org/wiki/OSI_model

Table of Contents
=================

* [Linux Networking Nomad](#linux-networking-nomad)
* [Table of Contents](#table-of-contents)
* [Context](#context)
   * [Network Sharing](#network-sharing)
      * [Tools](#tools)
      * [File servers](#file-servers)
   * [Network Basics](#network-basics)
      * [Network Components](#network-components)
      * [Network Addressing](#network-addressing)
      * [OSI Model (Open Systems Interconnection)](#osi-model-open-systems-interconnection)
      * [TCP/IP Model (layer from top to bottom)](#tcpip-model-layer-from-top-to-bottom)
      * [TCP/IP Model Example: Sending Email](#tcpip-model-example-sending-email)
         * [Sender](#sender)
         * [Receiver](#receiver)
      * [DHCP Overview](#dhcp-overview)
   * [Subnetting](#subnetting)
      * [IPv4](#ipv4)
      * [IPv6](#ipv6)
      * [Subnets](#subnets)
         * [Subnet Mask](#subnet-mask)
         * [CIDR](#cidr)
      * [NAT](#nat)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Network Sharing

### Tools
- `scp`: Security copy through SSH
- `rsync`: Remote file-copying tool
    - Difference between `scp`: break-point continuing
    - Flags:
        - `v`: verbose output
        - `r`: recursive into directory
        - `h`: human readable
        - `z`: compress for data transferring

### File servers
- `NFS`: Network file system
- `SAMBA`: Windows SMB protocol file server

## Network Basics

### Network Components
- `ISP`: Internet Service Provider
- `Router`: Connect local machine to Internet (through wifi or cable)
- `WAN`: Wide Area Network
- `WLAN`: Wireless Local Area Network
    - Network between router and wireless devices
- `LAN`: Local Area Network
    - Network between wired router and wired devices
- `Hosts`: Machine on a network

### Network Addressing
- `MAC Addresses`: Media Access Control Addresses (Hardware)
    - Unique identifier used as a hardware address
- `IP Address`: Internet Protocol Addresses (Software)
- `Hostname`: Human readable address for IP address
    - e.g. `localhost` -> `127.0.0.1`

### OSI Model (Open Systems Interconnection)
- Theoretical model of networking https://en.wikipedia.org/wiki/OSI_model

### TCP/IP Model (layer from top to bottom)
- `Application Layer`
    - Display packet data in user-friendly format
    - Protocols
        - `HTTP` (Hypertext Transfer Protocol), default port: 80
        - `SMTP` (Simple Mail Transfer Protocol), default port: 25
    - Packet contains
        - `Header`
            - Information about where the packet is going and where it came from
        - `Payload`
            - Actual data being transferred
- `Transport Layer`
    - Data transmission, checking port and file integrity, also file delivering
    - Protocols
        - `TCP` (Transmission Control Protocol)
            - Reliable data delivery
            - Better for data integrity
            - Use port to transfer data
        - `UDP` (User Data Protocol)
            - unreliable data delivery
- `Network Layer`
    - Encapsulate packet with IP packet
    - Move packets between hosts and across networks
    - Protocols
        - `IP` (Internet Protocol)
            - Route packets to other machine
        - `ICMP` (Internet Control Message Protocol)
            - Error message and debugging information
- `Link Layer`
    - Encapsulated packet into frame
    - Hardware specific layer
    - Physical link to hardware
    - Protocols
        - `ARP` (Address Resolution Protocol)
            - Used within the same network
            - Find MAC address associated with an IP address

### TCP/IP Model Example: Sending Email

#### Sender
1. `Application Layer`
    - Send email (data) to transport layer
2. `Transport Layer`
    - Data is encapsulated into TCP/UDP header to form a segment.
        - Attaches destination and source port information
    - Segment then is sent to network layer
3. `Network Layer`
    - TCP segment is encapsulated inside a IP packet
        - Attaches destination and source IP address
    - IP packet then is sent to link layer
4. `Link Layer`
    - IP packet is encapsulated into frame
        - Attaches destination and source MAC address
    - Frame is transmitted to Internet through physical hardware

#### Receiver
1. `Link Layer`
    - Receive frame from Internet
    - De-encapsulate frame contents into IP packet
    - Send IP packet to network Layer
2. `Network Layer`
    - De-encapsulate the IP packet into segment
    - Check destination IP, then send segment to transport layer
3. `Transport Layer`
    - De-encapsulate the segment
    - Check TCP/UDP port number and make a connection to application layer
4. `Application Layer`
    - Receive data from transport layer

### DHCP Overview
- DHCP (Dynamic Host Configuration Protocol)
- DHCP assigns IP address, subnet masks and gateway to machines
    - This is like phone number is assigned from mobile company

## Subnetting

### IPv4
- IP address composed by 4 octets
    - 1 octets (byte) has 8 bits (starts from 0 to 255 in decimal)

### IPv6
- IP address composed by 6 octets

### Subnets
- Group of hosts with IP address that are similar in a certain way
    - e.g. `123.45.67.8` and `123.45.67.9` are on the same subnet
    - This is like zip code for sending mails

#### Subnet Mask
- Determines network/host portion of IP address
    - e.g. `255.255.255.0` -> first 3 bytes are network portion, last 1 byte is host portion
- Combined network prefix and subnet mask
    - e.g. `123.234.0.0/255.255.0.0`
- Usage
    - Easier to control network flow of hosts within same subnet
    - Hosts in same subnet can communicate with each other but not available for other subnet
    - A router is needed to communicate with other subnets

#### CIDR
- CIDR (Classless Inter-Domain Routing)
- CIDR is used to represent subnet mask in a more compact way
    - By directly indicates the amount of bits used as the network prefix
    - e.g. `123.234.24.0/23` means the first 23 bits are used
        - Also means only 9 bits left for subnet (IPv4 has 32 bit in total)
        - Therefore for the number of usable subnet addresses is `2^9 - 2 = 510`
            - Here subnet address and broadcast address must be excluded

### NAT
- NAT (Network Address Translation)
- NAT makes router act as an intermediary between Internet and private network
    - i.e. Use a single IP to represent an entire group of computers
