# 3.1 数据链路层的功能

- 为网络层提供服务
  - 无确认的无连接服务：以太网
  - 有确认的无连接服务：无线通信
  - 有确认的面向连接服务
- 链路管理
  - 主要用于面向连接的服务
- 帧定界 帧同步 透明传输
  - HDLC 协议
  - 最大传送单元 MTU
- 流量控制
  - 对于数据链路层来说，控制的是相邻结点之间数据链路上的流量
  - 对于传输层来说，控制的是源端到目的端之间的流量
- 差错控制
  - 循环冗余校验 CRC
  - 自动请求重传 ARQ Automatic Repeat reQuest

## 习题

- 7 下列协议中，不是数据链路层的标准的是？

A ICMP
B HDLC
C PPP
D SLIP

答案是 A ICMP 是网络层的协议，PPP 是在 SLIP 的基础上发展而来
平常我们用的 ping 指令就是使用了 ICMP 协议
