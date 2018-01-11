The filter expression consists of one or more primitives. Primitives usually consist of an id(name or number) preceded by one or more qualifiers. There are three different kinds of qualifier:

* type: type qualifiers say what kind of thing the id name or number refers to. Possible types are **host**, **net**, **port** and **portrange**.
* dir: dir qualifiers specify a particular transfer direction to and/or from id. Possible directions are **src**, **dst**, **src or dst**, **src and dst**, **ra**, **ta**, **addr1**, **addr2**, **addr3**, and **addr4**.  The **ra**, **ta**, **addr1**, **addr2**, **addr3**, and **addr4** qualifiers are only valid for IEEE 802.11 Wireless LAN link layers.
* proto: proto qualifiers restrict the match to a particular protocol. Possible protos are: **ether**, **fddi**, **tr**, **wlan**, **ip**, **ip6**, **arp**, **rarp**, **decnet**, **tcp** and **udp**.



In addition to the above, there are some special `primitive' keywords that don't follow the pattern: **gateway**, **broadcast**, **less**, **greater** and arithmetic expressions.

More complex filter expressions are built up by using the words **and**, **or** and **not** to combine primitices. To save typing, identical qualifier list can be omitted.



Allowable primitives are:

**dst** **host** *host*

**src** **host** *host*

**host** *host*

**ether** **dst** *ehost*

**ether** **src** *ehost*

**ether** **host** *ehost*

**gateway** *host*

**dst** **net** *net*

**src** **net** *net*

**net** *net*

**net** *net* **mask** *netmask*

**net** *net|len*

**dst** **port** *port*

**src** **port** *port*

**port** *port*

**dst** **portrange** *port1-port2*

**src** **portrange** *port1-port2*

**portrange** *port1-port2*

*expr relop expr*

**less** *length*

**greater** *length*

**ip** **proto** *protocol* : *Protocol* can be a number or one of the names **icmp**, **icmp6**, **igmp**, **igrp**, **pim**, **ah**, **esp**, **vrrp**, **udp**, or **tcp**. Note that the identifiers **tcp**, **udp** and **icmp** are also keywords and must be escaped via backslash(\\). Note that this primitive does not chase the protocol header chain.

**ip6** **proto** *protocol*

**proto** *protocol*

**ip6** **protochain** *protocol*

**ip** **protochain** *protocol*

**protochain** *protocol*

**ether** **broadcast**

**ip** **broadcast**

**ether** **multicast**

**ip** **multicast**

**ip6** **mutlicast**

**ether** **proto** *protocol*

**ifname** *interface*

**on** *interface*



If an identifier is given without a keyword, the most recent keyword is assumed. For example,

​	**not host vs and ace**

is short for

​	**not hsot vs and host ace**

which should not be confused with

​	**not ( host vs or ace )**

