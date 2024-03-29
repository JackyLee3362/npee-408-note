# 1.1 操作系统的基本概念

## 操作系统的概念

控制和管理整个计算机系统的硬件与软件资源，合理地组织、调度计算机的工作与资源的分配，进而为用户和其他软件提供方便接口与环境的程序的集合

## 操作系统的特征

【并发】 Concurrence

- 并发是指两个或多个事件在**同一个时间间隔**内发生
- 【并发】 和 【并行】 的区别：注意与并行（**同一时刻**）的区别

【共享】 Sharing

- 互斥共享方式：比如打印机、磁带机虽然可以供多个进程使用，但是一段时间内只运行一个进程访问该资源
- 同时访问方式

【虚拟】Virtual

- 虚拟技术 - 时分复用技术，如处理器的分时共享 - 空分复用技术，如虚拟存储器

【异步】Asynchronism

- 操作系统两个最基本的特征是―并发 共享

## 操作系统的目标和功能

## 操作系统作为计算机系统资源的管理者

- 处理机管理
- 存储器管理
- 文件管理
- 设备管理

## 操作系统作为用户与计算机硬件系统之间的接口

命令接口

- 程序接口 | 批处理命令接口
- 联机命令接口 | 交互式命令接口

程序接口

- 概念：程序接口由一系列系统调用组成
- 应用：图形用户界面 graphical user interface GUI

操作系统用作扩充机器

- 没有任何软件支持的计算机称为【裸机】

## 习题

- 8【2009】单处理机系统中，可以并行的是
  A. 进程与进程
  B. 处理机与设备
  C. 处理机与通道
  D. 设备与设备 →B.C.D.，因为单处理系统，同一时刻只能有一个进程占用处理机
- 13 系统调用的目的是
  A 请求系统服务
  B 中止系统服务
  C 系统调用
  D 子程序 →A
- 16 操作系统与用户通信接口通常不包括
  A shell
  B 命令解释器
  C 广义指令
  D 缓存管理指令 →D，广义指令就是系统调用指令，而命令解释器属于命令接口，shell 是命令解释器，也属于命令接口。系统中的缓存全部由操作系统管理，对用户是透明的，操作系统不提供管理系统缓存的系统调用
- 19 【2013】计算机开机后，操作系统最终被加载到
  A BIOS
  B ROM
  C EPROM
  D RAM→D，BIOS 是一组固化到计算机内主板上的一个 ROM 芯片上的程序，它保存着计算机最重要的输入输出的程序、开机后的自检程序和系统自启动程序
- 综合题 1 说明库函数和系统调用的区别和联系 → 答案
  库函数是语言或应用程序的一部分，可以运行在用户空间中
  而系统调用是操作系统的一部分，是内核为用户提供的程序接口，运行在内核空间中，而且许多库函数都会使用系统调用来实现功能
  未使用系统调用的库函数，其执行效率通常要比系统调用的高。因为使用系统调用时，需要上下文的切换及状态的转换（由用户态转向核心态）
