# firewalld: Dynamic Firewall Manager
Learning note for firewalld

- Reference
    - https://www.youtube.com/watch?v=sA_MBFD-gLA
    - https://www.youtube.com/watch?v=By96TD00t2o&list=PLGXpVQQsgtaKgD4xT_rwq4Th_rIOHkz9r&index=47 (Chinese)
    - https://www.youtube.com/watch?v=QcJrxw49hXo&list=PLGXpVQQsgtaKgD4xT_rwq4Th_rIOHkz9r&index=48 (Chinese)
    - https://www.youtube.com/watch?v=AyyW87gfNzw&list=PLGXpVQQsgtaKgD4xT_rwq4Th_rIOHkz9r&index=49 (Chinese)
    - https://www.youtube.com/watch?v=a6OTU451hTA&list=PLGXpVQQsgtaKgD4xT_rwq4Th_rIOHkz9r&index=50 (Chinese)
    - https://blog.gtwang.org/linux/centos-7-firewalld-command-setup-tutorial/2/

# Context

## What is `firewalld`
- `firewalld` is a dynamical firewall manager which uses zone for network interface firewall setup
- `firewalld` works as frontend for `iptables`, but note they cannot be activated at the same time
    - `iptables` is another firewall manager comes before `firewalld`
- General `firewalld` connection strategy
    - Connection from external world to server is blocked by default
    - Connection from server to external world is permitted by default
    - Strategies of connection from external world are set into zones for different conditions

### Zones
- Default Zones and their conditions
    - `block`: All input connections are blocked
    - `work`/`home`: Trust external machines, all input are not blocked
    - `dmz`: Only accept input connections that are enabled
    - `public`: Only accept input connections that are enabled
    - `trusted`: All input connections are accepted
    - `drop`: All input connections are rejected
    - `external`: Only accept input connections that are enabled
- `firewalld` use `xml` to stores information of zones
    - `/usr/lib/firewalld/zones/*.xml`
- Zone and interface
    - One interface can only belong to one zone, but one zone can contain multiple interfaces
    - Zones that have assigned interfaces are active zones except `trusted`
        - `trusted` is activated once trusted rule is set
- Example setup that combines multiple zones: Source-on-white-list-only Setup
    - drop: set as default zone to reject all other sources in `trusted`
    - trusted: add sources as candidates for white list

## Start `firewalld`
Note that `firewall-cmd` command needs root privilege

To check if `firewalld` is activated, in terminal
1. `systemctl status firewalld`: It should show `active`
2. `firewall-cmd --state`: It should show `running`

If `firewalld` is not activated
1. `systemctl start firewalld`
2. `systemctl enable firewalld`

## Manage `firewalld`
Note that
- `--permanent` flag is needed to change the `firewalld` permanently (after reboot)
- `firewall-cmd --reload` command is needed every time to reload new `firewalld` configuration

### Manage Zones
- `firewall-cmd --list-all-zones`
    - List all zones of `firewalld`
- `firewall-cmd --get-default-zone`
    - Get default zone
- `firewall-cmd --get-active-zones`
    - Get active zones
- `firewall-cmd -set-default-zone=NEW_DEFAULT_ZONE`
    - Set default zone to zone NEW_DEFAULT_ZONE
- `firewall-cmd --zone=NEW_ZONE --change-interface=INTERFACE`
    - Change interface INTERFACE to zone NEW_ZONE
- `firewall-cmd --zone=NEW_ZONE --add-interface=INTERFACE`
    - Add interface INTERFACE to zone ZONE
- `firewall-cmd --zone=NEW_ZONE --remove-interface=INTERFACE`
    - Remove interface INTERFACE from zone ZONE
- `firewall-cmd --get-zone-of-interface=INTERFACE`
    - Get zone that has interface INTERFACE

### Manage Sources
Source example: `192.168.0.1/24`

- `firewall-cmd --permanent --zone=ZONE --add-source=IP/SUBNET`
    - Add source to zone ZONE
- `firewall-cmd --permanent --zone=ZONE --remove-source=IP/SUBNET`
    - Remove source to zone ZONE

### Manage Services
Service example: `ftp`, `ssh` (Note the port to use is defined in xml file)

- `firewall-cmd --get-services`
    - List all services that firewall can recognize
- `firewall-cmd --zone=ZONE --list-services`
    - List all active services in zone ZONE
- `firewall-cmd --zone=ZONE --add-service=SERVICE`
    - Add service to zone ZONE

### Manage IP set
Use IP set to manage multiple IPs

-  Create `ipset`
    1. `firewall-cmd --permanent--new-ipset=iplist --type=hash:ip`
        - Generate new ipset with name IPSET (flag `--permanent` is needed)
    2. `firewall-cmd --reload`
        - Reload firewalld to add the new ipset IPSET
    3. `firewall-cmd --ipset=IPSET --add-entry=IP`
        - Add IP to the new created IPSET
        - Continuously input
            ```
            firewall-cmd --ipset=IPSET --add-entry=IP_1
            firewall-cmd --ipset=IPSET --add-entry=IP_2
            firewall-cmd --ipset=IPSET --add-entry=IP_3
            ...
            ```
    4. `firewalll-cmd --zone=ZONE --add-source=ipset:IPSET`
        - Add ipset:iplist to zone ZONE
- Remove existing `ipset`
    1. `firewalld-cmd --permanent --delete-ipset=IPSET`
        - Remove existing ipset IPSET

### Manage Port/Protocol

Protocol example: `tcp`, `udp`
- `firewall-cmd --zone=ZONE --add-protocol=PROTOCOL`
    - Add protocol PROTOCOL to zone ZONE
- `firewall-cmd --zone=ZONE --remove-protocol=PROTOCOL`
    - Remove protocol PROTOCOL from zone ZONE

Port example: `1025-65535/tcp`, `1025-65535/udp`
- `firewall-cmd --zone=ZONE --add-port=PORT`
    - Add port PORT to zone ZONE
- `firewall-cmd --zone=ZONE --remove-port=PORT`
    - Remove port PORT to zone ZONE

### Masquerading Settings
Masquerading Setting is a boolean

- `firewall-cmd --zone=ZONE --add-masquerade`
    - Enable masquerade to zone ZONE
- `firewall-cmd --zone=ZONE --remove-masquerade`
    - Disable masquerade to zone ZONE

### Port Forwarding Settings
Define port and protocol for port forwarding

- `firewall-cmd --zone=ZONE --add-forward-port=port=PORT:proto=PROTOCOL:toport=TO_PORT`
    - Enable port forward from port PORT using protocal PROTOCOL to port TO_PORT
- `firewall-cmd --zone=ZONE --remove-forward-port=port=PORT:proto=PROTOCOL:toport=TO_PORT`
    - Disable port forwarding from port PORT using protocal PROTOCOL to port TO_PORT
