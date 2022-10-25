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
   * [Routing](#routing)
      * [What is a Router](#what-is-a-router)
      * [Routing Table](#routing-table)
      * [Path of a Packet](#path-of-a-packet)
         * [How a packet travels within its local network](#how-a-packet-travels-within-its-local-network)
         * [How a packet travels outside its network](#how-a-packet-travels-outside-its-network)
      * [Routing Protocols](#routing-protocols)
         * [Distance Vector Protocols](#distance-vector-protocols)
         * [Link State Protocols](#link-state-protocols)
         * [Border Gateway Protocol](#border-gateway-protocol)
   * [Network Config](#network-config)
      * [Network Interfaces](#network-interfaces)
      * [Route](#route)
      * [Dhclient](#dhclient)
      * [Network Manager](#network-manager)
      * [ARP](#arp)
   * [Troubleshooting](#troubleshooting)
      * [ICMP](#icmp)
      * [Ping](#ping)
      * [Traceroute](#traceroute)
      * [Netstat](#netstat)
      * [Package Analysis](#package-analysis)
   * [DNS](#dns)
      * [What is DNS](#what-is-dns)
      * [DNS Components](#dns-components)
      * [DNS Process](#dns-process)
      * [DNS on machine](#dns-on-machine)
      * [DNS Setup](#dns-setup)
      * [DNS Tools](#dns-tools)

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

## Routing

### What is a Router
- Router port
    - LAN port: Port for local network
    - WAN port: Port for wider network (e.g. Internet)
- Hops
    - Number of routers that packets move across
    - Use as distance indicator for packets
- Switching, Routing, Flooding
    - Switching: Receive packet and forward data to the destination device
    - Routing: Create the routing table to do switching better
    - Flooding: Used before routing. If a router don't know where to send the packet, it send packet to every outgoing links

### Routing Table
- Routing table
    - `sudo route -n`: show routing table
- Routing table components
    - Destination: IP address that packets go to
        - If IP address is `0.0.0.0`, it means address is not specified or unknown
    - Gateway: Packet destination that not on the same network
    - Genmask: subnet mask
    - Flags:
        - `UG`: Network is up and is a gateway
        - `U`: Network is up
    - Iface: Interface (e.g. Ethernet device labeled as eth0)

### Path of a Packet

#### How a packet travels within its local network
1. Local machine compares the destination IP to check if it is in the same subnet
2. Use ARP to broadcat a request on the local network to find the MAC address of destination host
3. With source/destination MAC addresses and source/destination IP addresses known, a packet can travel within local network

#### How a packet travels outside its network
1. Local machine compares the destination IP to check if it is not in the local network
2. After checking routing table, packet will be sent to gateway (another router).
   However, the MAC address of gateway is needed to send a packet.
   Therefore, packet send an ARP request to get the MAC address of the default gateway.
3. If the packet not gets forwarded to the same network, it will continue checking the routing table.
    - Note: Every time the packet moves,
        - It strips the old source and destination MAC address and updates
          the packet with new source and destination MAC address
        - It does not change the source or destination IP address
4. Once the packet gets forwarded to the same network, use ARP to find the final destination MAC address

### Routing Protocols
- Help system to adapt to network changes
- When routing path is agreed by all routers passed through, it is called `convergence`

#### Distance Vector Protocols
- Send signal periodically to determine the path of other networks by calculating the hop count a packet take across the network
- Next route is set to the one with the least amounts of hops
- Disadvantage:
    - In large network, it is hard to sends signal all around network to check hops
    - The protocol only cares number of hops instead of efficiency (e.g. bandwidth) of router
- e.g. RIP (Routing Information Protocol)
    - Broadcast routing table to every router in the network every 30 seconds.
    - RIP limiting hop number is 15

#### Link State Protocols
- Send update to neighboring routes
- Use algorithm to calculate the shortest path
- e.g. OSPF (Open Shortest Path First)
    - Only updates the routing tables if there was a network change
    - No hop limit is set

#### Border Gateway Protocol
- Use to collect and exchange routing information among autonomous systems
    - e.g. Internet

## Network Config

### Network Interfaces
- `ifconfig`: tool to configure network interface
    - `ifconfig -a `
        - Show network interface
    - `ifconfig eth0 192.168.2.1 netmask 255.255.255.0 up`
        - Assign an IP address and netmask to the eth0 interface and turn it up
    - `ifup/ifdown eth0`
        - Turn on/of eth0 interface
- `ip`: show/manipulate routing, network devices, interfaces and tunnels
    - `ip link show`
        - Show interface information for all interfaces
    - `ip -s link  show eth0`
        - Show the statistics of eth0 interface
    - `ip link set eth0 up/down`
        - Turn on/off eth0 interface
    - `ip address show`
        - Show IP addresses allocated to interfaces
    - `ip address add 192.168.1.1/24 dev eth0`
        - Add an IP address to eth0 interface

### Route
- Add a new Router
    - `sudo route add -net 192.168.2.1/23 gw 10.11.12.3`
    - `ip route add 192.168.2.1/23 via 10.11.12.3`
- Delete a route
    - `sudo route del -net 192.168.2.1/23`
    - `ip route delete 192.168.2.1/23 via 10.11.12.3`
    - `ip route delete 192.168.2.1/23`

### Dhclient
- `sudo dhclient`
    - obtain a fresh IP

### Network Manager
- `nmcli`
    - command to control and modify NetworkManger

### ARP
- Procedure to check ARP (that records IP-MAC associated mapping)
    - First check locally stored ARP cache
    - If a packet destination not in the ARP cache (e.g. after rebooting)
        1. The source host create the Ethernet frame with an ARP request packet
        2. The source host broadcast this frame to the entire network
        3. If one of the hosts on the network knows the correct MAC address,
           it will send a reply packet and frame containing the MAC address
        4. The source host add the IP to the MAC address mapping to the ARP cache
- Check ARP cache
    - `arp`
    - `ip neighbour show`

## Troubleshooting

### ICMP
- ICMP (Internet Control Message Protocol)
- ICMP is part of the TCP/IP protocol suite, it used to send update and error massages for debugging
- Common ICMP types
    - Type 0 - Echo Reply
    - Type 3 - Destination Unreachable
        - Code 0 - Network Unreachable
        - Code 1 - Host Unreachable
        - and etc.
    - Type 8 - Echo Request
    - Type 11 - Time Exceeded
    - and etc.

### Ping
- Used to test whether a packet can reach a host
- How ping works
    1. Send ICMP echo request (Type 8) packet to destination host
    2. Wait for an ICMP echo reply (Type 0) from target
- `ping`
    - `icmp_seq`: Sequence number of packets sent
    - `ttl`: The ttl (Time To Live) is used as hop counter
    - `time`: Roundtrip time took from sending request packet to getting an echo reply

### Traceroute
- Used to see how packets are getting routed
- How traceroute works
    1. Send packet with increasing TTL values, starting with 1
    2. When the first router gets packet, it decrements the TTL by 1
       and then send back a ICMP Time Exceeded message
    3. Send a new packet with TTL of 2. When the first router get packet,
       TTL decreased by 1 and then goes to the second router. After the seconds
       router get packet, TTL decreased to 0 and then send back a ICMP Time Exceeded message
    4. Repeat step 1-3 until the final destination is reached

### Netstat
- Socket and Port
    - Socket
        - Interface that allows program to send/receive data
        - Socket address: combination of IP address and port
        - Every connection between a host and a destination requires a unique socket
    - Port
        - Used to identify which application should send/receive data
            - e.g.
                - ftp: 21/tcp
                - ssh: 22/tcp
                - http: 80/tcp
                - https: 443:tcp
        - `/etc/services`: List of well-known port
- `netstat`: Print network related information
    - `netstat -a`: Show listening and non-listening sockets for network connection, including
        - `Proto`: Protocol used, TCP or UDP
        - `Recv-Q`: Data that is queued to be received
        - `Send-Q`: Data that is queued to be sent
        - `Local Address`: Locally connected host
        - `Foreign Address`: Remotely connected host
        - `Socket State`: The state of the socket
            - `LISTENING`: Listening for incoming connection
            - `SYN_SENT`: Actively attempting to establish a connection
            - `ESTABLISHED`: Connection established
            - `CLOSE_WAIT`: Remote host has shutdown and local machine waiting for the socket to close
            - `TIME_WAIT`: Waiting after close to handle packets still in the network

### Package Analysis
- `Wireshark`
- `tcpdump`
    - `sudo tcpdump -i wlan0`: Capture packet data on wlan0 interface
        - timestamp
        - IP
        - source and destination address
        - seq
        - length
    - `sudo tcpdump -w /some/file`: Write tcpdump output to a file

## DNS

### What is DNS
- DNS (Domain Name System)
- A distributed database of hostname to IP address

### DNS Components
- `Name Server`
    - Loads up DNS settings and configurations. Resolve hostname to IP address
    - Type of name server
        - Authoritative: Server holds actual DNS records
        - Recursive: Server that ask other servers until it founds a authoritative server
- `Zone File`
    - Store information about the domain and how to get to the domain if it does not know
    - Resource Records
        - Record name
        - TTL
        - Class: Namespace of the record information (e.g IN stands for Internet)
        - Type: Type of information stored in the record data (e.g. A for address)
        - Data: Depends on record type (e.g. A record -> IP address)

### DNS Process
- `Local DNS Server`
    - Talk to recursive DNS server
- `Root Servers`
    - 13 root server for the Internet, mirrored and distributed around the world to handle DNS requests for the Internet
    - Controlled by different organization
    - Contains information about top-level domains
    - `Top-level Domain (TLD)`
        - e.g. `.org`, `.com`, `.net` and etc.
- `Authoritative DNS Server`

### DNS on machine
- `/etc/hosts`
    - Contains mappings of some hostname to IP addresses
        - e.g. `127.0.0.1    localhost`
- `/etc/resolv.conf`
    - Map DNS name servers for more efficient lookups

### DNS Setup
- `BIND`
    - BIND (Berkeley Internet Name Domain)
    - Most popular DNS server and the standard that used with Linux distributions
- `DNSmasq`
    - Lightweight DNS server
    - Comes with tools needed for DHCP and DNS
- `PowerDNS`
    - Read information from multiple database such as MySQL

### DNS Tools
- `nslookup`: Name server lookup
- `dig`: Domain information groper
