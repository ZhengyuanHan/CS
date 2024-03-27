开放式系统互联模型（英语：Open System Interconnection Model，缩写：OSI；简称为OSI模型）是一种概念模型，一个试图使各种计算机在世界范围内互连为网络的标准框架。该模型将通信系统中的数据流划分为七个层，从分布式应用程序数据的最高层表示到跨通信介质传输数据的物理实现。每个中间层为其上一层提供功能，其自身功能则由其下一层提供。

## 第7层 应用层
应用层（Application Layer）是用户真正与电脑沟通的点，这一层只有在真正需要访问网络才有作用。该层常见的协议包括：TELNET、HTTP、FTP、WWW

## 第6层 表现层(表示层)
表现层（Presentation Layer）把数据转换为能与接收者的系统格式兼容并适合传输的格式。该层常见的协议包括：JPEG、MPEG、ASLL

## 第5层 会议层(会话层)
会议层（Session Layer）负责在数据传输中设置和维护计算机网络中两台计算机之间的通信连接。该层常见的协议包括：SQL、NFS、NETBIOS、RPC 

## 第4层 传输层
传输层（Transport Layer）把传输表头（TH）加至资料以形成分组。传输表头包含了所使用的协议等发送信息。例如:传输控制协议（TCP）等。该层常见的协议包括：TCP、UDP、SPX

## 第3层 网络层
网络层（Network Layer）决定数据的路径选择和转寄，将网络表头（NH）加至数据包，以形成分组。网络表头包含了网络资料。例如:互联网协议（IP）等。该层常见的协议包括：IP、IPX、OSFP、RIP、IGRP、ICMP、ARP、RARP 

## 第2层 数据链路层
数据链路层（Data Link Layer）负责网络寻址、错误侦测和改错。其分为两个子层：分为两个子层：逻辑链路控制（logical link control，LLC）子层和介质访问控制（Media access control，MAC）子层。该层常见的协议包括：Ethernet、VLAN、PPP、MAC、IEEE802.3、FR、HDLC

## 第1层 物理层(物理层)
物理层（Physical Layer）在局域网上传送数据帧（Data Frame），它负责管理电脑通信设备和网络媒体之间的互通。包括了针脚、电压、线缆规范、集线器、中继器、网卡、主机接口卡、路由器等。
