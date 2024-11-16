Tags: #CCNA
Vimwiki: :CCNA:

______________________________________________________________________

# FREE CCNA 200-301 - Day 01 - What is a Switch?

- Reference
  - [Course_youtube_link](https://www.youtube.com/watch?v=9eH16Fxeb9o&list=PLIhvC56v63IJVXv0GJcl9vO5Z6znCVb1P&index=2)

# Table of Contents

- [FREE CCNA 200-301 - Day 01 - What is a Switch?](#free-ccna-200-301---day-01---what-is-a-switch)
  - [Context](#context)
    - [Hub (device before switch)](#hub-device-before-switch)
    - [Switch](#switch)
    - [More about layers](#more-about-layers)
    - [Wireless switch](#wireless-switch)
    - [CCNA Example](#ccna-example)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Hub (device before switch)

- How hub sends message between machines connected to it?
  1. Receive message from the machine sending message
  2. Send message to all machines connected to it except the sending one
  - In short, hub just repeat the message it received

## Switch

- How switch sends message between machines connected to it?
  1. Receive message from the machine sending message
  2. Send message only to the receiver assigned by sender
  - In short, switch only send the message to the right receiver
- How switch knows which one is the right receiver?
  - Switch recognizes connected machine by MAC address (layer 2 address)
    - IP address is layer 3 address (Switch can not recognize)
    - Physical Internet is layer 1
  - Switch stores MAC address, ports in MAC table (Content-addressable Memory (CAM) table)

## More about layers

- Layer 2: switch, MAC address, frame (message)
- Layer 3: IP address, packet (message)

## Wireless switch

- It works like a hub, broadcasting to all connected machines

## CCNA Example

1. Which of the following addresses will a switch use to populate the CAM table

   - \[ \] destination IP address
   - \[ \] source IP address
   - \[ \] destination MAC address
   - \[x\] source MAC address
   - Switch do not know anything about IP address

2. Which of the following addresses will a switch use to make forwarding decisions?

   - \[ \] source MAC address
   - \[ \] source IP address
   - \[ \] destination IP address
   - \[x\] destination MAC address
   - Switch do not know anything about IP address
