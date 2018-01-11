##### TCPDUMP OUTPUT FORMAT

* Timestamps  *hh:mm:ss.frac*


* TCP Packets

  ​	TCP协议的通常输出格式:

  ​		src > dst: Flags [tcpflags], seq data-seqno, ack ackno, win window, urg urgent, options [opts], length len

  ​		[tcpflags] : S indicates SYN,  . indicates ACK,  P indicates PUSH, etc.

  ​		tcp[flags] indicates tcp[13]

  ​		tcp[tcp-fin], tcp[tcp-rst], tcp[tcp-push], tcp[tcp-ack], tcp[tcp-urg], tcp[tcp-syn]

* DNS请求:

  ​	src > dst: id op? flags qtype qclass name (len)

* DNS响应:

  ​	src > dst: id op rcode flags a/n/au type class data (len)

详细请查看 [tcp-output-format](http://www.tcpdump.org/manpages/tcpdump.1.html#lbAG)

