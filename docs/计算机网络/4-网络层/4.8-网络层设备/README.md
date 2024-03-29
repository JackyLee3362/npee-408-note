# 4.8 网络层设备

## 路由器的组成和功能 Router

- 组成
  - 交换结构
  - 一组输入端口
  - 一组输出端口
- 功能
  - 分组转发
  - 路由计算
- 路由表 路由转发
- 路由表是根据路由选择算法得出的
- 与网桥的区别
  - 网桥与高层协议无关，而路由器是面向协议的
- 路由表：| 目的网络 IP 地址 | 子网掩码 | 下一跳 IP 地址 | 接口 |

## 习题

- 13 在路由表中设置一条默认路由，则其目的地址和子网掩码分别置为?→0.0.0.0; 0.0.0.0
- z-2 简述路由器的路由功能和转发功能
- 综合题 3【2019】 ![]()
  - 某网络拓扑如图所示，其中 R 为路由器，主机 H1~H4 的 IP 地址配置及 R 的各接口 IP 地址配置如图所示，现有若干以太网交换机（无 VLAN 功能）和路由器两类网络互联设备可供选择
    A. 设备 1、设备 2、设备 3 分别应该选择什么类型的网络设备？
    B. 设备 1、设备 2、设备 3 中，哪几个设备的接口需要配置 IP 地址？ 为对应的接口配置正确的 IP 地址
    C. 为确保主机 H1~H4 能够访问 Internet，R 需要提供什么服务？
    D. 若主机 H3 发送了一个目的地址为 192.168.1.127 的 IP 数据报，网络中哪几个主机会收到该数据？
- 路由器 Router
