# LINUX

https://haydenjames.io/mastering-linux-administration-20-powerful-commands-to-know/
https://haydenjames.io/90-linux-commands-frequently-used-by-linux-sysadmins/
https://haydenjames.io/linux-networking-commands-scripts/
https://haydenjames.io/50-essential-linux-commands-that-you-should-know/

systemctl show

Requisite
Conflicts
Requires
RequiredBY

Wants
WantedBy

# PYTHON

## collection

Counter
namedtuple
OrderDict #default in python > 3.6
deque

## itertools

product
permutations
combinations
combination_with_replacement
accumulate
groupby

count
cycle
repeat

## json

dumps
loads
JSONEncoder
JSONDecoder

## functools

## sys

getsizeof

atool
7zip
mpv-mpris

# VIM

ctrl+x
gn move and select
dot operation only take effects when modifying text
semi-column/comma operation only take effects when navigating text
o/O change visual mode direction

# Networking

## Physical Layer

ip link show

## Datalink Layer

ip neightbor show
arp

## Network Layer

ip address show

## Transportation Layer

ss -tupln

apt-file search
apt-file list

Parallel
parallel --line-buffer
parallel --ungroup

timeout

nmap -sn 192.168.6.0/24

/etc/resolv.conf
systemd-resolve
resolvectl
/etc/NetworkManager/system-connections
https://www.nslookup.io/learning/what-is-a-dns-resolver/

nmcli connection modify Hotspot 802-11-wireless-security.pmf 1
https://askubuntu.com/questions/1424633/unable-to-connect-with-the-hotspot-created-on-ubuntu

## fuser

fuser -v -m /dev/sdb1
fuser -v /dev/jordankhwu/73FF-F83C
fuser -k /dev/jordankhwu/73FF-F83C
fuser -v -n tcp 6463

- DNF/YUM Repository:
  - `/etc/yum.repos.d/`
- Flatpak:
  - `/var/lib/flatpak/app`
  - `$HOME/.var/app`
- Xsession:
  - `/usr/share/xsessions`

command ls -d /usr/share/themes/\* | xargs -L 1 basename

~/.config/gtk-3.0/settings.ini
gtk-application-prefer-dark-theme=1

~/.config/gtk-4.0/settings.ini
gtk-application-prefer-dark-theme=1

lsmod
modinfo
dmesg
lshw
lsblk
