# 2.1 进程和线程

## 进程的概念和特征 Process

### 概念

进程是进程实体的运行过程，是系统进行资源分配和调度的一个独立单位

进程存在的唯一标志―进程控制块

### 特征

- 动态性
- 并发性
- 独立性
- 异步性
- 结构性

## 进程的状态与转换

- 运行态
- 就绪态
- 阻塞态
- 创建态
- 结束态
- 前 3 种是基本状态
- 状态的转换
  - 就绪态 → 运行态
  - 运行态 → 就绪态
  - 运行态 → 阻塞态
  - 阻塞态 → 就绪态
  - 一个进程从运行态变成阻塞态是主动还是被动行为―主动行为
  - 从阻塞态变成就绪态是主动行为还是被动行为―是被动行为，需要其他相关进程的协助

## 进程控制

- 进程的创建：创建原语
- 进程的终止：撤销原语
  - 引起进程终止的事件主要有 ↓
    - 正常结束
    - 异常结束
    - 外界干预
- 进程的阻塞和唤醒：阻塞原语（Block）、唤醒原语（Wakeup）
- 进程切换

## 进程的组织

### 进程控制块 Process Control Block, PCB

实例

- 进程描述信息
  - 进程描述符 PID Process ID
  - 用户描述符 UID User ID
- 进程控制和管理信息
  - 当前进程状态
  - 进程优先级
  - ...
- 资源分配清单
- 处理机相关信息

### 程序段―能被进程调度程序调度到 CPU 执行的程序代码段

### 数据段―可以是进程对应的程序加工处理的原始数据，也可以是程序执行时产生的中间或最终结果

### 进程的通信

#### 低级通信方式―PV 操作

#### 高级通信方法

- 共享存储
- 消息传递：直接通信方式 和 间接通信方式
- 管道通信―是消息传递的一种特殊方式
  - 限制管道大小
  - 读进程也可能工作得比写进程快
  - 注意―从管道读数据时一次性操作，数据一旦被读取，就被管道抛弃

### 线程概念和多线程模型

## 线程 Thread

- 概念：可以简单地理解为「轻量级进程」，是一个基本的 CPU 执行单元
- 组成
  - 线程 ID
  - 程序计数器
  - 寄存器集合
  - 堆栈
- 基本状态
  - 就绪
  - 阻塞
  - 运行
- 进程与线程的区别
  - 调度：线程是独立调度的基本单位，进程是拥有资源的基本单位
  - 拥有资源： 进程是拥有资源的基本单位，而线程不拥有系统资源（除了一点点必不可少的资源）
  - 并发性：
  - 系统开销：
  - 地址空间和其他资源：进程的地址空间之间相互独立，统一进程的各线程共享进程的资源，某进程内的线程对于其他进程不可见
  - 通信方面：进程间通信（IPC）需要进程同步和互斥手段的辅助，以保证数据的一致性
- 线程的属性 ↓
  - 线程是一个轻型实体，它不拥有系统资源，但每个线程都应有一个唯一的标识符和一个线程控制块，线程控制块记录线程执行的寄存器和栈等现场状态
  - 不同线程可以执行相同的程序，即同一个服务程序被不同的用户调用时，操作系统把它们创建成不同的线程
  - 同一进程的各个线程共享该进程所拥有的资源
  - 线程是处理机的独立调度单位，多个线程是可以并发执行的
  - 一个线程被创建后，便开始了它的生命周期，直至终
- 线程的实现方式
  - 用户级线程 User-Level Thread, ULT
  - 内核级线程 Kernel-Level Thread, KLT ，也称为内核支持的线程
- 多线程模型：有些系统同时支持用户线程和内核线程，由此产生了不同的多线程模型
  - 多对一模型―将多个用户级线程映射到一个内核级线程
  - 一对一模型―将每个用户及线程映射到一个内核级线程
  - 多对多模型―将 N 个用户及线程映射到 M 个内核级线程上，（N ≥ M）

## 习题

- 2 下列关于线程的叙述中，正确的是
  A 线程包含 CPU 现场，可以独立执行程序
  B 每个线程有自己的独立空间
  C 进程只能包含一个线程
  D 线程之间的通信必须使用系统调用函数 → 答案
  A 正确
  B 错误 线程没有自己独立的地址空间，它共享其所属进程的空间
  C 错误 进程可以包含多个线程
  D 错误 可以直接使用共享空间
- 4 进程和程序的根本区别是 → 静态和动态的特点。动态性是进程最重要的特点，以此来区分文件形式的静态程序
- 8 在单处理系统中，若同时存在 10 个进程，则处于就绪队列中的进程最多有几个 →9
- 10 系统进程所请求的一次 I/O 操作完成后，将使进程从什么态 变为 什么态 → 阻塞态变为就绪态
- 12 并发进程失去封闭性，是指并发进程共享变量，其执行结果与其速度有关，为什么？→ 进程的封闭性是指进程执行的结果不会随着执行得快慢而改变，但是失去封闭性后，不同速度下的执行结果不同
- 14 「进程之间可能是无关的，但也可能是有交互性的」→ 正确
- 17 用信箱实现进程间互通信息的通信机制有两个通信原语，它们是 → 发送原语和接收原语
- 20 指出下列 C 语言程序中的内容及相关数据结构位于哪一段？
  A. 全局赋值变量
  B. 未赋值的全局变量
  C. 函数调用实参传递值
  D. 用 malloc()要求动态分配的存储区
  ⑤ 常量值（比如 1995，“string"）
  ⑥ 进程的优先级 → 答案
  正文段：全局赋值变量、常量值
  栈段：未赋值的全局变量、函数调用实参传递值
  堆段，用 malloc()要求动态分配的存储区
  PCB：进程的优先级
  C 语言编写的程序在使用内存时一般分为三个段，正文段，数据堆段，数据栈段
  二进制代码和常量存放在正文段
  动态分配的存储区在数据堆段
  临时使用的变量在数据栈段
- 22 系统动态 DLL 库中的系统线程，被不同的进程所调用，它们是相同还是不同的的线程？→ 相同，程序代码经过多次创建可对应不同的进程，而同一个系统的进程（或线程）可以由系统调用的方法被不同的进程（或线程）多次使用
- 27 在具有通道设备的单处理器系统中实现并发技术后，「各进程在某一时间段并发运行，CPU 和 I/O 设备间并行工作」→T
- 29 指令 原语 信号量 信箱
- 30【2010】导致创建新进程的操作是
  A. 用户登录成功
  B. 设备分配
  C. 启动程序执行 →A.C. ，设备分配是通过在系统中设置相应的数据结构实现的，不需要创建进程，这是操作系统中 I/O 核心子系统的内容
- 32 「线程的引入增加了程序执行时的时空开销」→ 错误 引入线程是为了减少时空开销
- 33 「同一进程或不同进程内的线程都可以并发执行」→ 正确
- 42 进程处于「 」时，它处于非阻塞态
  A 等待从键盘输入数据
  B 等待协作进程的一个信号
  C 等待操作系统分配 CPU 时间
  D 等待网络数据进入内存 →C，处于阻塞态是由于某个事件不满足而等待，这样的事一般是 I/O 操作，如键盘等，或是因互斥或同步数据引起的等待，如等待信号或等待进入互斥临界区代码段等，等待网络数据进入内存是为了进程同步，而等待 CPU 调度的进程属于就绪态
- 49【2014】
  「进程对管道进行读操作或者写操作都可能被阻塞」
  「一个管道只能有一个读进程或一个写进程对其操作」→T，F，管道类似于通信中的半双工通信，同一时刻最多有一个方向的传输，不能两个方向同时进行
- 53【2019】下列关于线程的描述中，错误的是
  A 内核级线程的调度由操作系统完成
  B 操作系统为每个用户级线程建立一个线程控制块
  C 用户及线程间的切换比内核级间的切换效率高
  D 用户级线程可以在不支持内核级线程的操作系统上实现 → 答案
  B，「操作系统为每个用户线程建立一个线程控制块」属于一对一模型
- Z 完全没做
