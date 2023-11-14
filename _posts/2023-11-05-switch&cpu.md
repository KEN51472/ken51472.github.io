---
layout: detail
type : 5
keyword : RAID
title: RAID
description: 
---

## 广播风暴（Broadcast Storm）
计算机网络中，当有大量广播数据包在网络中传输时，网络中的所有设备都会接收这些广播数据包并进行处理，从而导致网络性能下降或网络崩溃的现象。广播风暴通常发生在以下情况下：

1. 网络中有大量广播数据包：

有大量广播数据包在网络中传输时，网络中的所有设备都会接收这些广播数据包并进行处理，导致网络性能下降或网络崩溃。

2. 网络中存在环路：

网络中存在环路时，广播数据包会在环路上不断循环，导致广播数据包的数量不断增加，最终导致广播风暴的发生。

3. 网络中存在多个广播域：

网络中存在多个广播域时，广播数据包会在所有广播域中传播，导致广播数据包的数量不断增加，最终导致广播风暴的发生。


为了避免广播风暴的发生，可以采取以下措施：

1. 使用交换机替代集线器：

交换机可以根据MAC地址表实现点对点的数据传输，避免了广播数据包在网络中传播的问题，从而避免了广播风暴的发生。

2. 使用虚拟局域网（VLAN）技术：

VLAN技术可以将不同的设备划分到不同的虚拟局域网中，从而避免广播数据包在整个网络中传播，从而避免广播风暴的发生。

3. 配置合理的网络拓扑结构：

在网络设计和配置时，应该避免出现环路和多个广播域，从而避免广播风暴的发生。

## 交换机 集线器 路由器

交换机、集线器和路由器在网络中的使用场景有所不同：

交换机Switch：

适用于局域网LAN内部的设备连接，如办公室、数据中心等。
用于连接多台计算机、服务器、打印机等设备，提供高性能的数据交换和通信。
适合于要求高带宽、低延迟和大量数据传输的环境，如视频会议、大型文件传输等。

集线器Hub：

集线器是一种较为简单的设备，在现代网络中已经很少使用。
适用于简单的小型网络，或者特定的测试和调试场景。
不适合要求高性能和大量数据传输的环境，因为它会导致数据冲突和带宽浪费。

路由器Router：

适用于连接不同的网络，如连接不同的局域网、连接局域网和广域网WAN、连接到互联网等。
用于实现不同网络之间的数据路由和转发，提供网络间的通信和互联互通。
适合于企业、ISP（互联网服务提供商）、家庭网络等需要连接多个网络的场景。
总的来说，交换机适合于在局域网内部提供高性能的设备连接和数据交换；集线器在现代网络中使用较少，主要适用于简单的小型网络；而路由器适合于连接不同的网络，实现网络间的路由和通信。

## OSI七层模型

网络的七层架构从下到上主要包括物理层、数据链路层、网络层、传输层、会话层、表示层和应用层；  

物理层：主要定义物理设备标准，它的主要作用是传输比特流，具体做法是在发送端将1 、0 转化为电流强弱来进行传输，在到达目的地后再将电流强弱转化为l 、0 ， 也就是我们常说的模数转换与数模转换，这一层的数据叫作比特
数据链路层：主要用于对数据包中的MAC 地址进行解析和封装。这一层的数据叫作数据帧。在这一层工作的设备是网卡、网桥、交换机
网络层：主要用于对数据包中的 IP 地址进行封装和解析，这一层的数据叫作数据包。在这一层工作的设备有路由器、交换机、***等
传输层：定义了传输数据的协议和端口号，主要用于数据的分段、传输和重组。在这一层工作的协议有TCP 和UDP 等。 TCP 是传输控制协议，传输效率低，可靠性强，用于传输对可靠性要求高、数据量大的数据，比如支付宝转账使用的就是 TCP; UDP 是用户数据报协议，与TCP 的特性恰恰相反，用于传输可靠性要求不高、数据量小的数据，例如抖音等视频服务就使用了UDP 。
会话层：在传输层的基础上建立连接和管理会话，具体包括登录验证、断点续传、数据粘包与分包等。在设备之间需要互相识别的可以是IP ， 也可以是MAC 或者主机名。
表示层：主要对接收的数据进行解释、加密、解密、压缩、解压缩等，即把计算机能够识别的内容转换成人能够识别的内容（图片、声音、文字等）
应用层：基于网络构建具体应用，例如FTP 文件上传下载服务、Telnet 服务、HTTP 服务、DNS 服务、SNMP 邮件服务等

交换机工作于OSI参考模型的第二层，即数据链路层。交换机内部的CPU会在每个端口成功连接时，通过将MAC地址和端口对应，形成一张MAC表。在今后的通讯中，发往该MAC地址的数据包将仅送往其对应的端口，而不是所有的端口。因此，交换机可用于划分数据链路层广播，即冲突域；但它不能划分网络层广播，即广播域。

## TCP/IP模型

TCP/IP模型是一个网络协议栈：

应用层：应用层协议定义了应用程序之间的通信和交互规则，例如HTTP、FTP、SMTP等协议。

传输层：传输层协议提供了端到端的数据传输服务，例如TCP和UDP协议。

网络层：网络层协议负责在不同的网络之间传输数据，例如IP协议。

数据链路层：数据链路层协议负责在同一网络中传输数据，例如以太网协议。

TCP/IP模型是互联网标准协议栈，设计目标是为了实现分布式计算机系统之间的通信和数据交换，因此它被广泛应用于互联网和局域网中。

与OSI模型相比，TCP/IP模型的层数更少，更加简单明了，而且它的实现更加灵活和高效。虽然有些协议不完全符合TCP/IP模型的定义，但是TCP/IP模型仍然是网络通信的基础。
