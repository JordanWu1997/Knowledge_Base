https://zh.wikipedia.org/zh-tw/Tcpdump
https://www.youtube.com/watch?v=v7C70Wc1hsA
https://www.youtube.com/watch?v=eAiacqxwMxU&t=57s
https://www.youtube.com/watch?v=zgBZ007_lY8
https://zh.wikipedia.org/zh-tw/Tcpdump

tcpdump -c 10 -w test.log # save dumped packets

tcpdump -r test.log # read dumped log

tcpdump -D # list interface

tcpdump -i wlp3s0 # interface

tcpdump -vvv # even more verbose

tcpdump -n # numeric

tcpdump tcp/udp/stmp/icmp

tcpdump port 80

tcpdump portrange 1-1024

tcpdump src port 80
tcpdump src 192.168.1.1

tcpdump dst port 80
tcpdump dst 192.168.1.1

tcpdump host google.com

tcpdump greater 1000 # Unit: byte

tcpdump less 10 # Unit: byte

tcpdump -A # ASCII code

tcpdump -X # Hex code and ASCII code

tcpdump tcp and port 443 # AND operation
tcpdump tcp or port 4433 # OR operation
tcpdump not tcp # NOT operation
