tcpdump    \[-AbdDefhHIJKlLnNOpqStuUvxX#]   \[-B *buffer-size*]

​	\[-c *count*]  \[-C *file-size*]

​	\[-w *file*] \[-r *file*] \[-V *file-list*]

​	\[-s *snaplen*]

​	[-Q *in|out|inout*]

​	[-i *network-interface*]

`-A`  以ASCII码的方式打印除去链路层首部的数据包，这对于捕获网页的数据包非常有用。

`-B buffer`

`--buffer-size=buffer-size`

​	设置操作系统捕获数据包的缓存大小， 以K(1024 bytes)为单位。

`-D`

`--list-interfaces`

​	相当于`ifconfig -a`

`-e`

​	打印链路层帧首部，该选项可用于打印以太网的MAC地址。

`-F file`

​	从 `file`中读取表达式，命令行中的所有额外表达式都会被忽略。

`-i interface`

`--interface=interface`

​	侦听interface接口。如若未指定侦听接口，将配置侦听接口为最小数字的接口(回环接口除外)，比如eth0

`--immediate-mode`

​	立即模式， 该模式下，数据包一旦抵达就分发到tcpdump，而不是为了提高效率而缓存。这是输出到终端而非文件或管道时的默认模式。

`-K`

`--dont-verify-checksums`

​	不要尝试校验IP、TCP、UDP的校验和。

`-l`

​	将stdout配置成行缓冲。如果在捕获时想查看数据该选项时有用的。比如下列命令: 

​	`tcpdump -l | tee dat`

​	`tcpdump -l > dat & tail -f dat`

`-n`

​	不要转换地址(例如主机地址和端口号等)到名称。

`-N`

​	不要打印全称域名(FQDN-Full Qualified Domain Name)。

`#`

`--number`

​	在捕获行的开头打印一个数字(递增)。

`-O`

`--no-optizmize`

​	不要运行数据包捕获代码优化器。该选项在你怀疑优化器有bug时有用。

`--print`

​	打印解析的数据包输入，即使制定了`-w`标志。

`-Q direction`

`--direction=direction`

​	选择捕获的数据包方向(`in`或`out`或`inout`)。

`-q`

​	仅仅输出协议信息以保持输出行尽可能的短。

`-r file`

`-w file`

`-V file-list`

​	指定输入输出文件。

`-S`

`--absolute-tcp-sequence-numbers`

​	打印绝对而非相对TCP序列号。

`-T type`

​	强迫输出特定类型的数据包， 目前已知的类型有`aodv` `carp` `cnfp` `lmp` `pgm` `tftp` `rpc` `rtp`  `snmp`等。

`-t`  :  不要打印时间戳

`-tt` `-ttt` `-tttt` `-ttttt`  : 打印时间戳，精度由低到高。

`-v` `-vv` `-vvv` : 冗余输出，冗余程度由低到高。

`-x`

​	以十六进制的格式输出数据帧(不包括链路层帧)的头部及数据，填充的字节也将被输出。

`-xx`

​	以十六进制的格式输出数据帧(包括链路层帧)的头部及数据。

`-X`

​	以十六进制和ASCII码的格式输出数据帧(不包括链路层帧)的头部及数据。

`-XX`

​	以十六进制和ASCII码的格式输出数据帧(包括链路层帧)的头部及数据。

`expression`

​	过滤表达式。







