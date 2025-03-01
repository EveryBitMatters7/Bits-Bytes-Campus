## 🔍第 2 章 链路层和局域网（答案附后）

## 一、单选题（每题 3 分，共 30 分）

1. 链路层中的数据包被称为（ ）。
   - A. 分组
   - B. 帧
   - C. 报文
   - D. 数据报
2. 在数据链路层广泛使用的检错技术是（ ）。
   - A. 奇偶校验
   - B. 循环冗余检验 CRC
   - C. 海明码校验
   - D. 都不是
3. CSMA/CD 协议用于（ ）。
   - A. 无线局域网
   - B. 以太网
   - C. 令牌环网
   - D. 广域网
4. MAC 地址的长度是（ ）。
   - A. 32 位
   - B. 48 位
   - C. 64 位
   - D. 128 位
5. 以太网帧结构中，前同步码的作用是（ ）。
   - A. 实现 MAC 帧的比特同步
   - B. 标识源地址
   - C. 标识目的地址
   - D. 检验帧的正确性
6. 以太网交换机是（ ）设备。
   - A. 物理层
   - B. 链路层
   - C. 网络层
   - D. 传输层
7. VLAN 的作用不包括（ ）。
   - A. 改善性能
   - B. 增加广播域范围
   - C. 简化管理
   - D. 降低成本
8. 以下哪种不是划分 VLAN 的方法（ ）。
   - A. 基于交换机端口
   - B. 基于 IP 地址
   - C. 基于协议类型
   - D. 基于 MAC 地址
9. 802.1Q 帧比标准以太网帧增加的字段是（ ）。
   - A. VLAN 标记
   - B. 源地址
   - C. 目的地址
   - D. 校验和
10. 关于以太网的说法，错误的是（ ）。
    - A. 是主流有线局域网技术
    - B. 提供可靠连接
    - C. 简单、便宜、速度快
    - D. 采用 CSMA/CD 协议

## 二、多选题（每题 5 分，共 25 分）

1. 链路层的作用包括（ ）。
   - A. 差错检测
   - B. 广播信道多接入复用
   - C. 链路层寻址
   - D. 提供网络层服务
2. 常用的信道复用技术有（ ）。
   - A. TDMA
   - B. FDMA
   - C. CDMA
   - D. CSMA/CD
3. ARP 协议的作用是（ ）。
   - A. 实现 IP 地址到 MAC 地址的转换
   - B. 实现 MAC 地址到 IP 地址的转换
   - C. 用于链路层寻址
   - D. 用于网络层寻址
4. 以太网帧结构包含的字段有（ ）。
   - A. 目的地址
   - B. 源地址
   - C. 数据
   - D. CRC 校验码
5. 虚拟局域网 VLAN 的优点有（ ）。
   - A. 改善安全性
   - B. 简化管理
   - C. 降低成本
   - D. 改善性能

## 三、简答题（每题 15 分，共 45 分）

1. 简述循环冗余校验 CRC 的原理及计算过程。
2. 说明 CSMA/CD 协议的工作过程及特点。
3. 阐述 VLAN 的概念、作用及划分方法。

# 第 2 章 链路层和局域网 答案

## 一、单选题

1. B
2. B
3. B
4. B
5. A
6. B
7. B
8. B
9. A
10. B

## 二、多选题

1. ABC
2. ABC
3. AC
4. ABCD
5. ABCD

## 三、简答题

1. **CRC 原理**：在发送端，先把数据划分为组，假定每组 k 个比特，在每组 M 后面添加供差错检测用的 n 位冗余码，一起发送出去。冗余码计算：用二进制的模 2 运算进行 2ⁿ乘 M 的运算，得到的 (k + n) 位的数除以事先选定好的长度为 (n + 1) 位的除数 P，得出商是 Q 而余数是 R，余数 R 比除数 P 少 1 位，将余数 R 作为冗余码拼接在数据 M 后面。接收端对收到的每一帧进行 CRC 检验，若得出的余数 R = 0，则判定这个帧没有差错，接受；若余数 R≠0，则判定这个帧有差错，丢弃。
2. **CSMA/CD 协议工作过程**：网卡从网络层收到数据报文，包装成帧。如果 NIC 检测到信道空闲，则开始发送数据；反之，则等待直至信道空闲，然后发送数据。在发送帧的过程中检测到发生碰撞，则中止发送，并发送拥塞信号，进入二进制指数退避，重传 16 次仍不能成功，则丢弃该帧，并向更高层次的协议报告。
   **特点**：发送数据前先监听广播信道，短时间内侦测是否发生碰撞，发生碰撞时停止发送并等待随机时间后重发；其性能比 ALOHA 好，简单、便宜、完全去中心化，但使用该协议的以太网只能进行半双工通信。
3. **VLAN 概念**：虚拟局域网 VLAN 是由一些局域网网段构成的与物理位置无关的逻辑组，这些网段具有某些共同需求，每一个 VLAN 的帧都有一个明确的标识符，指明发送这个帧的计算机属于哪一个 VLAN。
   **作用**：改善性能、简化管理、降低成本、改善安全性。
   **划分方法**：基于交换机端口、基于计算机网卡的 MAC 地址、基于协议类型、基于 IP 子网地址、基于高层应用或服务。