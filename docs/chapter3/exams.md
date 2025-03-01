## 🔍第 3 章 网络层 - 数据平面（答案附后）

## 一、单选题（每题 3 分，共 30 分）

1. 网络层向运输层提供的服务是（ ）。
   - A. 面向连接的可靠服务
   - B. 无连接的尽最大努力服务
   - C. 面向连接的尽最大努力服务
   - D. 无连接的可靠服务
2. IP 地址是给每个连接在互联网上的主机或路由器分配的（ ）位标识符。
   - A. 32
   - B. 48
   - C. 64
   - D. 128
3. 以下属于 A 类 IP 地址的是（ ）。
   - A. 128.11.3.31
   - B. 10.2.0.37
   - C. 192.5.48.3
   - D. 223.255.255.254
4. 子网掩码的作用是（ ）。
   - A. 标识 IP 地址的类型
   - B. 找出 IP 地址中的子网部分
   - C. 区分网络层和链路层
   - D. 用于 IP 地址的转换
5. IP 数据报首部中，总长度字段表示的是（ ）。
   - A. 首部的长度
   - B. 数据部分的长度
   - C. 首部和数据之和的长度
   - D. 最大传送单元 MTU 的长度
6. 以下关于 NAT 的说法，错误的是（ ）。
   - A. 可以解决 IP 地址紧缺问题
   - B. 分为 NAT 和 NAPT 两种实现方式
   - C. 违背了端对端原则
   - D. 能提高网络的安全性，不需要其他安全措施
7. IPv6 将地址从 IPv4 的 32 位增大到了（ ）位。
   - A. 64
   - B. 128
   - C. 256
   - D. 512
8. IP 数据报分片后，片偏移字段以（ ）为偏移单位。
   - A. 1 字节
   - B. 2 字节
   - C. 4 字节
   - D. 8 字节
9. 在 IP 数据报首部中，生存时间 TTL 字段的作用是（ ）。
   - A. 指示数据报在网络中可通过的路由器数的最大值
   - B. 表示数据报的优先级
   - C. 用于检验数据报首部的正确性
   - D. 标识数据报的类型
10. 路由器中，负责将分组从输入端口的缓存发送到合适输出端口缓存的是（ ）。
    - A. 路由处理器
    - B. 交换结构
    - C. 输入端口
    - D. 输出端口

## 二、多选题（每题 5 分，共 25 分）

1. 网络层的关键作用有（ ）。
   - A. 路由
   - B. 转发
   - C. 差错检测
   - D. 流量控制
2. 分类 IP 地址包括（ ）。
   - A. A 类
   - B. B 类
   - C. C 类
   - D. D 类
3. IP 数据报首部的固定部分包含的字段有（ ）。
   - A. 版本
   - B. 首部长度
   - C. 标识
   - D. 协议
4. NAT 的实现方式有（ ）。
   - A. 纯粹的地址转换
   - B. 基于端口的地址转换
   - C. 基于 MAC 地址的转换
   - D. 基于 IP 子网的转换
5. IPv6 的主要变化包括（ ）。
   - A. 更大的地址空间
   - B. 扩展的地址层次结构
   - C. 灵活的首部格式
   - D. 支持即插即用

## 三、简答题（每题 15 分，共 45 分）

1. 简述虚电路服务与数据报服务的区别。
2. 说明 IP 地址的分类及特点。
3. 阐述 NAT 的工作原理及两种实现方式的特点。





# 第 3 章 网络层 - 数据平面 答案

## 一、单选题

1. B
2. A
3. B
4. B
5. C
6. D
7. B
8. D
9. A
10. B

## 二、多选题

1. AB
2. ABCD
3. ABCD
4. AB
5. ABCD

## 三、简答题

1. 虚电路服务与数据报服务区别：
   虚电路服务思路是可靠通信由网络保证，通信前需建立虚电路，每个分组使用短的虚电路号，属于同一条虚电路的分组按同一路由转发，能保证分组顺序，端到端的差错处理和流量控制可由网络或用户主机负责；
   数据报服务思路是可靠通信由用户主机保证，发送分组无需建立连接，每个分组有完整终点地址，独立选择路由转发，分组到达终点不一定按发送顺序，端到端的差错处理和流量控制由用户主机负责。
2. IP 地址分类：分为 A、B、C、D、E 五类。A 类地址网络号占 1 字节，主机号占 3 字节；B 类地址网络号占 2 字节，主机号占 2 字节；C 类地址网络号占 3 字节，主机号占 1 字节；D 类地址是多播地址；E 类地址保留为今后使用。
   特点：是一种分等级的地址结构，方便管理且可减小路由表大小；标志一个主机或路由器和一条链路的接口；用转发器或网桥连接的局域网具有同样的网络号；所有分配到网络号的网络都是平等的。
3. NAT 工作原理：在专用网连接到互联网的路由器上安装 NAT 软件，装有 NAT 软件的路由器至少有一个有效的外部全球 IP 地址。所有使用本地地址的主机在和外界通信时，都要在 NAT 路由器上将其本地地址转换成全球 IP 地址。
   两种实现方式特点：
   纯粹的地址转换（NAT），现实中较少使用，它在内部主机与外部主机通信时，离开专用网替换源地址，进入专用网替换目的地址；
   NAPT 利用地址加端口进行转换，NAT 路由器只需要一个全球 IP 地址，通过端口号区分不同本地主机，能同时连接超过六万台本地主机，但它是 “有争议性” 的、“临时” 的解决手段，违背端对端原则，NAT 后的主机不能同时作为服务器向外提供服务。