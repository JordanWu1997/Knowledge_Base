# Transmission Control Protocol (TCP)
- https://www.youtube.com/watch?v=Iuvjwrm_O5g

# Context

## Purpose
- Work in transportation layer
- Connection-oriented that assures data integrity during the transmission
    - Provide reliability even in poor network connection

## 3-way Handshake
To establish connection

1. Client sends `SYN` packet to server
2. Server receives `SYN` packet and sends `SYN+ACK` packet back to client
3. Client receives `SYN+ACK` packet and sends `ACK` packet to server
    - To make sure the connection is established

### Why 3-way Handshake instead of 2-way Handshake ? Case Study
If network is not very reliable, the first `SYN` packet from client might lost in the middle of the way.
In that case, the client will send a new `SYN` packet to server, and once server receive the second `SYN` packet, it will send `SYN+ACK` packet and wait.
However, if the first `SYN` packet (lost one) reached server after the second `SYN` packet, server will treat these two packet as two connections.
So now, server think there are two connection from client, but client think there is only on connection, which is the problem of two-way handshake

### Packet Lost Problem and Order of Packet Problem
- Create buffering area stores the sending data in the order of index of packets
- Sender sends TCP packets that contains the start and the length of sending data in buffering area
- Receiver send `ACK` packet contains start and the length of sent data to confirm the receiving packet
- If the packets are lost, receiver can ask sender to send lost packets again

## 4-way Wavehand
To close connection

1. Client sends `FIN` packet to server
2. Server receives `FIN` packet and sends `ACK` packet to client. Server changes to `CLOSE-WAIT` stage
3. After all data transmission is done, server send `FIN` packet to client
4. Client receives `FIN` packet and sends `ACK` packet to server. Client changes to `TIME-WAIT` stage
    - Once server receives `ACK` packet, the connection from server is closed immediately
    - To make sure server receives the `ACK` packet, client waits until reaching time-out time, and client closes connection
        - If server does not receive the `ACK` packet, it will send `FIN` packet again
        - Once client receives `FIN` packet, the time-out time is refreshed and client sends `ACK` packet again
