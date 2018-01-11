##### TCPDUMP OUTPUT FORMAT

###### Timestamps  *hh:mm:ss.frac*

Link Level Headers

ARP/RARP Packets

IPv4 Packets

TCP Packets

​	The general format of a TCP protocol line is:

​		src > dst: Flags [tcpflags], seq data-seqno, ack ackno, win window, urg urgent, options [opts], length len

​		[tcpflags] : S indicates SYN,  . indicates ACK,  P indicates PUSH, etc.

​		tcp[flags] indicates tcp[13]

​		tcp[tcp-fin], tcp[tcp-rst], tcp[tcp-push], tcp[tcp-ack], tcp[tcp-urg], tcp[tcp-syn]

DNS Request

​	src > dst: id op? flags qtype qclass name (len)

DNS Response

​	src > dst: id op rcode flags a/n/au type class data (len)