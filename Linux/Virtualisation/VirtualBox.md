# Oracle VirtualBox

- https://www.youtube.com/watch?v=Wvf0mBNGjXY&t=4s

## Network Adapter

Network adapter in VM is not unique, you can add as much as 4

### 1. Host-Only Network

- VMs can talk to each other within private network assigned by host
- VMs cannot talk to public network
  - Port forwarding is required to access public network

### 2. Network Address Translation (NAT) Network

- VMs can talk to each other within private network assigned by host
- VMs can talk to public network with translated IP
  - IP is translated when teleport/receive data
- No system from public network can access private network VMs

### 3. Bridge Network

- VMs are assigned IP by LAN, which means they are now extensions of LAN
- VMs can talk to either private or public network
- System from public network can reach VMs

## Port Forwarding

1. Add rule in VirtualBox settings
   - Protocol: TCP (default: TCP)
   - Host Port: Port for SSH in local machine (Here is set: 2222)
   - Guest Port: Port for SSH in remote machine (default: 22)
1. In Remote Machine

- `systemctl start sshd`
  - Enable SSH server on remote machine

3. In Local Machine
   - `ssh USERNAME_ON_REMOTE_MACHINE@127.0.0.1 -p HOST_PORT`
     - Use ssh to connect to local port 2222
     - The connection will then be forwarding by NAT to remote machine port 22
