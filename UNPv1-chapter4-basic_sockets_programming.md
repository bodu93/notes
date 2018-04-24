产生RST的三个条件(`ECONNREFUSED`):

1. 目的地为某端口的SYN到达，然而该端口没有正在监听的服务器
2. TCP想取消一个已有连接(`SO_LINGER`)
3. TCP接收到一个根本不存在的连接上的分节(半打开连接)


UDP的ICMP差错:

1. 对错误的端口发起请求
2. 需要分片但是设置了DF标志(traceroute)



TCP的ICMP差错:

1. 源站抑制(source quench)： 当网卡接收速度大于主机处理速度。
2. 主机不可达或网络不可达(临时的断网或链路中路由器出问题)，TCP将不断重传报文，而被回送icmp unreachable错误，直到重传超时。

`connect()`调用可能返回的错误码:

`ETIMEOUT`  连接到对方主机超时，一般是75(bsd-based system)秒

`ECONNRESET`

`EHOSTUNREACH/ENETUNREACH`