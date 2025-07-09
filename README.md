# Networking Concepts Review Notes (中英复习笔记) - 完整版

This document provides a comprehensive, bilingual summary of the key networking concepts from your course materials, including detailed explanations, formulas, and practice questions.
本文档根据您提供的课程材料，对关键网络概念进行了全面、中英双语的总结，包含详细解释、计算公式及练习题。

---

## 1. Wired LAN: Ethernet (有线局域网：以太网)

*   **Ethernet:** A family of wired computer networking technologies commonly used in local area networks (LAN), metropolitan area networks (MAN), and wide area networks (WAN).
    *   **以太网 (Ethernet):** 一系列常用于局域网 (LAN)、城域网 (MAN) 和广域网 (WAN) 的有线计算机网络技术。
*   **IEEE 802.3 Standard:** The set of standards that defines Ethernet. It specifies the physical layer and the medium access control (MAC) sublayer of the data link layer.
    *   **IEEE 802.3 标准:** 定义以太网的标准集。它规定了数据链路层的物理层和介质访问控制 (MAC) 子层。
*   **CSMA/CD (Carrier Sense Multiple Access with Collision Detection):** The access method used by early Ethernet to handle simultaneous transmissions. Stations listen before transmitting, and if a collision occurs, they stop, wait a random amount of time, and retransmit. Modern switched Ethernet is full-duplex and does not use CSMA/CD.
    *   **载波侦听多路访问/碰撞检测 (CSMA/CD):** 早期以太网用于处理同时传输的访问方法。工作站在发送前先侦听信道，如果发生碰撞，则停止发送，随机等待一段时间后重新发送。现代的交换式以太网是全双工的，不再使用 CSMA/CD。
*   **MAC Address:** A unique 48-bit hardware address assigned to each network interface card (NIC) to identify a device on the network. It is typically represented as 12 hexadecimal digits (e.g., `00:1A:2B:3C:4D:5E`).
    *   **MAC 地址:** 分配给每个网络接口卡 (NIC) 的唯一 48 位硬件地址，用于在网络上识别设备。通常表示为 12 位十六进制数 (例如 `00:1A:2B:3C:4D:5E`)。
*   **Ethernet Frame:** The format in which data is transmitted over Ethernet. The structure includes:
    *   **以太网帧:** 以太网上传输数据的格式，其结构包括：
        *   **Preamble & SFD:** For synchronization. (前同步码和起始帧分界符：用于同步)
        *   **Destination & Source MAC Addresses:** 6 bytes each. (目标和源 MAC 地址：各 6 字节)
        *   **Type/Length:** Indicates the protocol of the payload (e.g., IPv4, IPv6) or the length. (类型/长度：指明负载数据的协议类型或长度)
        *   **Data Payload:** The actual data being sent (46 to 1500 bytes). (数据负载：实际发送的数据，大小为 46 到 1500 字节)
        *   **Frame Check Sequence (FCS):** 4-byte CRC for error detection. (帧校验序列：4 字节的 CRC，用于错误检测)

### Bridge in Wired LAN (有线局域网中的桥接器)
![image](https://github.com/user-attachments/assets/5db1cdf6-357c-4348-b986-a7dec7337dc8)

*   **Bridge (桥接器):** 一种数据链路层设备，用于连接两个或多个局域网段，并根据 MAC 地址转发数据帧。
    *   **With Bridge (使用桥接器):**
        *   **Benefits (优点):**
            *   **Reduces Collision Domains (减少冲突域):** 桥接器将一个大的冲突域分割成多个小的冲突域，从而减少了冲突的发生，提高了网络性能。
            *   **Filters Traffic (过滤流量):** 桥接器学习连接设备的 MAC 地址，只转发目标 MAC 地址在另一个网段的数据帧，从而减少了不必要的流量。
            *   **Improves Security (提高安全性):** 通过隔离流量，可以提高每个网段的安全性。
        *   **How it works (工作原理):** 桥接器维护一个 MAC 地址表，记录每个端口连接的设备 MAC 地址。当收到一个数据帧时，它会查找目标 MAC 地址，如果目标在同一个网段，则丢弃该帧；如果目标在另一个网段，则转发该帧到相应的端口。
    *   **Without Bridge (不使用桥接器):**
        *   **Limitations (缺点):**
            *   **Single Collision Domain (单一冲突域):** 所有设备都在同一个冲突域中，随着设备数量的增加，冲突发生的概率会大大增加，导致网络性能下降。
            *   **Broadcast Storms (广播风暴):** 广播流量会泛洪到所有设备，可能导致网络拥塞。
            *   **No Traffic Isolation (无流量隔离):** 所有流量都在同一个网段中传输，无法有效隔离不同部门或用户之间的流量。

---

## 2. Comparison: Wired vs. Wireless LAN (有线与无线局域网对比)

### Wired LAN (Ethernet) - Benefits & Limitations (有线局域网的优缺点)

*   **Benefits (优点):**
    *   **Speed & Bandwidth (速度与带宽):** Generally offers higher speeds (up to 10 Gbps and beyond) and more consistent bandwidth than wireless networks. (通常提供比无线网络更高的速度（高达 10 Gbps 或更高）和更稳定的带宽。)
    *   **Reliability & Stability (可靠性与稳定性):** Immune to radio frequency interference. Provides a stable connection with lower latency, which is crucial for gaming or real-time applications. (不受射频干扰影响。提供延迟更低的稳定连接，对游戏或实时应用至关重要。)
    *   **Security (安全性):** Inherently more secure as it requires physical access to a network port. Data is not broadcast through the air. (本质上更安全，因为它需要对网络端口的物理访问。数据不会在空中广播。)

*   **Limitations (缺点):**
    *   **Mobility (移动性):** Devices are physically tethered by a cable, offering no mobility. (设备被网线物理束缚，没有移动性。)
    *   **Installation (安装):** Can be difficult and costly to install, especially in older buildings or across long distances. (安装可能困难且昂贵，尤其是在旧建筑或长距离布线时。)
    *   **Clutter (杂乱):** Cables can be messy and create clutter. (线缆可能会很凌乱。)

### Wireless LAN (WLAN) - Benefits & Limitations (无线局域网的优缺点)

*   **Benefits (优点):**
    *   **Convenience & Mobility (便利性与移动性):** Allows users to connect to the network and move around freely within the coverage area. (允许用户连接到网络并在覆盖区域内自由移动。)
    *   **Easy Deployment & Scalability (易于部署和扩展):** Easy to set up where cables cannot be run. Adding new users is simple and does not require new wiring. (在无法布线的地方很容易设置。添加新用户很简单，不需要新的布线。)
    *   **Cost (成本):** Initial setup for a small area can be cheaper as it avoids the cost of extensive cabling. (小范围的初始设置成本可能更低，因为它避免了大量的布线成本。)

*   **Limitations (缺点):**
    *   **Security (安全性):** Wireless signals are broadcast and can be intercepted more easily. Requires strong encryption (like WPA3) to be secure. (无线信号是广播的，更容易被拦截。需要强大的加密（如 WPA3）来确保安全。)
    *   **Range (范围):** The signal has a limited range and can be weakened or blocked by walls, floors, and other physical obstructions. (信号范围有限，并且可能被墙壁、地板和其他物理障碍物削弱或阻挡。)
    *   **Reliability & Interference (可靠性与干扰):** Performance can be affected by interference from other Wi-Fi networks, Bluetooth devices, microwave ovens, and other electronics. (性能可能受到来自其他 Wi-Fi 网络、蓝牙设备、微波炉和其他电子设备的干扰影响。)
    *   **Speed (速度):** Typically slower than a wired connection, and the speed can fluctuate depending on signal strength and network congestion. (通常比有线连接慢，并且速度会根据信号强度和网络拥塞情况而波动。)

---

## 3. Wireless LAN (WLAN) Details (无线局域网详解)

*   **Wi-Fi (Wireless Fidelity):** A popular technology that allows electronic devices to connect to a WLAN, mainly using the IEEE 802.11 standards.
    *   **Wi-Fi (无线保真):** 一种流行的技术，允许电子设备连接到无线局域网 (WLAN)，主要使用 IEEE 802.11 系列标准。
*   **IEEE 802.11 Standards Comparison (标准对比):**
    *   **IEEE 802.11 标准:** 无线局域网的一系列规范。主要版本包括：
![image](https://github.com/user-attachments/assets/025f253d-57be-4d43-86d4-3466a6eb7494)


### WLAN Architecture (WLAN 架构)

*   **Station (STA):** Any device with a wireless network interface (e.g., laptop, smartphone).
    *   **工作站 (STA):** 任何带有无线网络接口的设备 (例如，笔记本电脑、智能手机)。
*   **Access Point (AP):** A device that creates a wireless local area network. It acts as a bridge between the wireless and wired networks.
    *   **接入点 (AP):** 创建无线局域网的设备。它充当无线和有线网络之间的桥梁。
*   **BSS (Basic Service Set):** A group of stations that can communicate with each other. The coverage area of an AP is a BSS.
    *   **基本服务集 (BSS):** 一组可以相互通信的工作站。一个 AP 的覆盖范围就是一个 BSS。
        *   **Independent BSS (IBSS) / Ad-hoc Mode:** An ad-hoc network where stations communicate directly without an AP.
        *   **独立 BSS (IBSS) / Ad-hoc 模式:** 一个没有 AP 的自组织网络，工作站之间直接通信。
        *   **Infrastructure BSS:** Stations communicate via an AP.
        *   **基础架构 BSS:** 工作站通过一个 AP 进行通信。
*   **ESS (Extended Service Set):** A set of two or more connected BSSs that appear as a single logical network to the user, allowing for roaming. The BSSs are connected by a Distribution System (DS).
    *   **扩展服务集 (ESS):** 两个或多个相连的 BSS 组成的集合，对用户来说如同一个单一的逻辑网络，允许漫游。这些 BSS 通过一个分布式系统 (DS) 连接。
*   **SSID (Service Set Identifier):** The name of a WLAN. You see this name when you search for Wi-Fi networks.
    *   **服务集标识符 (SSID):** WLAN 的网络名称。您在搜索 Wi-Fi 网络时看到的就是这个名字。

### WLAN Security (WLAN 安全)

*   **WEP (Wired Equivalent Privacy):** An old, insecure security protocol. **Do not use.**
    *   **有线等效保密 (WEP):** 一种过时且不安全的加密协议。**不要使用。**
*   **WPA/WPA2/WPA3 (Wi-Fi Protected Access):** Modern, secure standards for protecting wireless networks. WPA3 is the latest and most secure, offering stronger encryption and authentication.
    *   **Wi-Fi 保护访问 (WPA/WPA2/WPA3):** 用于保护无线网络的现代安全标准。WPA3 是最新、最安全的标准，提供更强的加密和身份验证。

---

## 4. IPv6 (互联网协议第 6 版)

*   **Reason for IPv6:** The massive growth of the internet led to the exhaustion of the IPv4 address space (only ~4.3 billion addresses).
    *   **IPv6 的原因:** 互联网的迅猛发展导致 IPv4 地址空间（仅约 43 亿个地址）耗尽。
*   **Key Features:**
    *   **主要特性:**
        *   **Larger Address Space:** 128-bit addresses (2¹²⁸, a virtually inexhaustible number).
        *   **更大的地址空间:** 128 位地址 (2¹²⁸，一个几乎用不完的数字)。
        *   **Simplified Header:** Faster processing by routers because fields like checksum and options are removed or handled differently.
        *   **简化的报头:** 路由器处理速度更快，因为校验和、选项等字段被移除或以不同方式处理。
        *   **Integrated Security:** IPSec is a mandatory part of the protocol, providing end-to-end security.
        *   **集成的安全性:** IPSec 是协议的强制组成部分，提供端到端安全。
        *   **No NAT (Network Address Translation):** End-to-end connectivity is possible at the IP layer, simplifying protocols and applications.
        *   **无网络地址转换 (NAT):** IP 层可以实现端到端连接，简化了协议和应用。
*   **Address Format & Abbreviation:**
    *   **地址格式与缩写:**
        *   **Format:** Eight groups of four hexadecimal digits, separated by colons (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
        *   **格式:** 八组四位十六进制数，以冒号分隔。
        *   **Rule 1: Leading Zeros:** Leading zeros in any group can be omitted (e.g., `0db8` becomes `db8`).
        *   **规则 1: 省略前导零:** 每组中的前导零可以省略。
        *   **Rule 2: Consecutive Zeros:** One sequence of consecutive all-zero groups can be replaced by a double colon `::` (e.g., `2001:0db8:85a3::8a2e:0370:7334`). This can only be done once in an address.
        *   **规则 2: 省略连续的零:** 一串连续的全零组可以用双冒号 `::` 代替。这个规则在每个地址中只能使用一次。

### IPv6 Address Types (IPv6 地址类型)

*   **Unicast:** An address for a single interface. A packet sent to a unicast address is delivered to the interface identified by that address. (one-to-one)
    *   **单播:** 单个接口的地址。发送到单播地址的数据包将被递送到该地址标识的接口。(一对一)
*   **Multicast:** An address for a set of interfaces (typically belonging to different nodes). A packet sent to a multicast address is delivered to all interfaces in the set. (one-to-many)
    *   **多播:** 一组接口（通常属于不同节点）的地址。发送到多播地址的数据包将被递送到该组中的所有接口。(一对多)
*   **Anycast:** An address for a set of interfaces, but a packet sent to an anycast address is delivered to just one of the interfaces in the set (the "nearest" one, according to the routing protocol's measure of distance). (one-to-one-of-many)
    *   **任播 (Anycast):** 一组接口的地址，但发送到任播地址的数据包只会被递送到该组中的一个接口（根据路由协议的距离度量，通常是“最近”的那个）。(多选一)

*   **Transition Mechanisms:**
    *   **过渡机制:**
        *   **Dual Stack:** Devices run both IPv4 and IPv6 simultaneously.
        *   **双栈:** 设备同时运行 IPv4 和 IPv6。
        *   **Tunneling (6to4, Teredo):** Encapsulating IPv6 packets within IPv4 packets to traverse an IPv4-only network.
        *   **隧道技术 (6to4, Teredo):** 将 IPv6 数据包封装在 IPv4 数据包中，以穿越仅支持 IPv4 的网络。

---

## 5. IPv4 Subnetting (IPv4 子网划分)

*   **VLSM (Variable Length Subnet Masking - 可变长子网掩码):** 一种 IP 地址分配策略，允许在同一个网络中使用不同长度的子网掩码，从而更有效地利用 IP 地址空间，减少浪费。
    *   **优点:** 提高 IP 地址利用率，减少地址浪费；支持更灵活的网络设计。
    *   **缺点:** 路由表可能更复杂；故障排除可能更困难。

### Key Concepts (关键概念)

*   **Network Address (网络地址):** 子网的第一个地址，用于标识整个子网。主机位全为 0。
*   **Broadcast Address (广播地址):** 子网的最后一个地址，用于向子网中的所有设备发送数据。主机位全为 1。
*   **Subnet Mask (子网掩码):** 用于区分 IP 地址中的网络部分和主机部分。网络位为 1，主机位为 0。
*   **Usable Host Address Range (可用主机地址范围):** 网络地址和广播地址之间的所有地址，可以分配给网络中的设备。
*   **Wasted IP Addresses (浪费的 IP 地址):** 每个子网中，网络地址和广播地址是不可用的，因此它们是“浪费”的。VLSM 的目标是最小化这种浪费。

### VLSM Calculation Steps (VLSM 计算步骤)

1.  **Identify Requirements (识别需求):** 列出所有子网所需的主机数量，并按降序排列（从大到小）。
2.  **Determine Subnet Mask (确定子网掩码):** 对于每个子网，根据所需主机数量计算出最小的子网掩码。公式为 `2^h - 2 >= N`，其中 `h` 是主机位数，`N` 是所需主机数量。
3.  **Allocate Addresses (分配地址):** 从可用的 IP 地址块中，为每个子网分配网络地址、广播地址和可用主机范围。始终从最大的子网开始分配，以确保有足够的连续地址空间。

---

## 6. Error Control & Flow Control (差错控制与流量控制)

### Error Detection (差错检测)

*   **Purpose (目的):** To detect errors that may occur during data transmission. (检测数据传输过程中可能发生的错误。)

    *   **2D Parity Check (二维奇偶校验):**
        *   **Description (描述):** Data is arranged in a table (rows and columns). Parity bits are calculated for each row and each column. A single bit error will result in parity errors in both its row and column, allowing for error detection and localization. (数据以表格形式（行和列）排列。为每行和每列计算奇偶校验位。单个比特错误将导致其行和列都出现奇偶校验错误，从而实现错误检测和定位。)
        *   **Example (示例):**
            ```
            Data: 1010 0110
            Row 1: 1 0 1 0 | 0 (even parity)
            Row 2: 0 1 1 0 | 0 (even parity)
            -----------------
            Col P: 1 1 0 0
            ```
            If `1010` becomes `1000`, row 1 parity changes, and column 3 parity changes.

    *   **Cyclic Redundancy Check (CRC) (循环冗余校验):**
        *   **Description (描述):** A powerful error-detection method. A sequence of redundant bits (CRC remainder) is appended to the end of a data block. This remainder is calculated by dividing the data polynomial by a predetermined generator polynomial using modulo-2 arithmetic. The receiver performs the same calculation; if the remainder is zero, no error is detected. (一种强大的差错检测方法。将一串冗余位（CRC 余数）附加到数据块的末尾。该余数是通过使用模 2 算术将数据多项式除以预定的生成多项式来计算的。接收方执行相同的计算；如果余数为零，则未检测到错误。)
        *   **Process (过程):**
            1.  **Sender (发送方):**
                *   Appends `n` zeros to the data (where `n` is the degree of the generator polynomial).
                *   Divides the augmented data by the generator polynomial using modulo-2 division.
                *   The remainder is the CRC. Replaces the appended zeros with this CRC.
            2.  **Receiver (接收方):**
                *   Divides the received data (including CRC) by the same generator polynomial.
                *   If the remainder is zero, the data is considered error-free.

### Flow Control (流量控制)

*   **Purpose (目的):** To ensure that the sender does not overwhelm the receiver with data. (确保发送方不会用数据压垮接收方。)

    *   **Stop-and-Wait ARQ (停止等待 ARQ):**
        *   **Description (描述):** The sender sends one frame and then waits for an acknowledgment (ACK) from the receiver before sending the next frame. If a frame or ACK is lost, a timeout mechanism triggers retransmission. (发送方发送一帧，然后等待接收方的确认 (ACK) 后再发送下一帧。如果帧或 ACK 丢失，超时机制会触发重传。)
        *   **Similarity to Go-Back-N/Selective Repeat (与回退 N/选择性重传的相似点):** All are ARQ protocols that use acknowledgments and timeouts for reliability.
        *   **Difference (不同点):** Only one frame is in transit at a time, leading to low efficiency, especially over long distances or high-latency links. (一次只有一个帧在传输中，导致效率低下，尤其是在长距离或高延迟链路上。)

    *   **Go-Back-N ARQ (回退 N ARQ):**
        *   **Description (描述):** The sender can send multiple frames (up to a window size N) without waiting for an ACK. If an error occurs (e.g., a frame is lost or corrupted), the receiver discards all subsequent frames and sends a negative acknowledgment (NAK) or a cumulative ACK for the last correctly received frame. The sender then retransmits the lost frame and all subsequent frames that were sent after it. (发送方可以发送多个帧（最多一个窗口大小 N），而无需等待 ACK。如果发生错误（例如，帧丢失或损坏），接收方会丢弃所有后续帧，并发送一个否定确认 (NAK) 或对最后正确接收的帧的累积 ACK。然后发送方重新传输丢失的帧以及之后发送的所有后续帧。)
        *   **Similarity to Stop-and-Wait (与停止等待的相似点):** Uses acknowledgments and timeouts. (使用确认和超时。)
        *   **Difference (不同点):** Allows multiple frames in flight, improving efficiency. However, it retransmits potentially many frames even if only one was lost. (允许多个帧在传输中，提高了效率。但是，即使只丢失了一个帧，它也会重新传输许多帧。)

    *   **Selective Repeat ARQ (选择性重传 ARQ):**
        *   **Description (描述):** Both sender and receiver maintain a window. The sender can send multiple frames. If a frame is lost, the receiver only requests retransmission of the specific lost frame. The receiver buffers out-of-order frames and delivers them to the network layer only after all missing frames are received and reordered. (发送方和接收方都维护一个窗口。发送方可以发送多个帧。如果帧丢失，接收方只请求重新传输特定的丢失帧。接收方缓冲乱序帧，并且只有在所有丢失的帧都接收并重新排序后才将其交付给网络层。)
        *   **Similarity to Go-Back-N (与回退 N 的相似点):** Allows multiple frames in flight. (允许多个帧在传输中。)
        *   **Difference (不同点):** More efficient than Go-Back-N as it only retransmits the lost or corrupted frames, reducing redundant transmissions. Requires more complex buffering at the receiver. (比回退 N 更高效，因为它只重新传输丢失或损坏的帧，减少了冗余传输。接收方需要更复杂的缓冲。)

---

## 7. Digital Signal Encoding & Synchronization (数字信号编码与同步)

### Digital Encoding Schemes (数字编码方案)

*   **Purpose (目的):** To convert digital data into digital signals for transmission over a medium. (将数字数据转换为数字信号，以便通过介质传输。)
*   **Key Concepts (关键概念):**
    *   **Signal Level (信号电平):** The voltage or power level used to represent bits. (用于表示比特的电压或功率电平。)
    *   **Bit Rate (比特率):** The number of bits transmitted per second (bps). (每秒传输的比特数。)
    *   **Baud Rate (波特率):** The number of signal elements (changes in signal level) per second. (每秒信号元素（信号电平变化）的数量。)
    *   **Synchronization (同步):** Ensuring the receiver's clock is aligned with the sender's clock to correctly interpret bits. (确保接收方的时钟与发送方的时钟对齐，以正确解释比特。)

*   **Common Encoding Schemes (常见编码方案):**

    *   **NRZ-L (Non-Return-to-Zero, Level) (不归零电平码):**
        *   **Description (描述):** A positive voltage represents 0, and a negative voltage represents 1 (or vice versa). The signal level does not return to zero between bits. (正电压表示 0，负电压表示 1（反之亦然）。信号电平在比特之间不返回零。)
        *   **Pros (优点):** Simple to implement, efficient use of bandwidth. (实现简单，带宽利用率高。)
        *   **Cons (缺点):** No self-synchronization (long sequences of 0s or 1s can cause clock drift), DC component (cannot pass through transformers). (无自同步能力（长串的 0 或 1 会导致时钟漂移），存在直流分量（无法通过变压器）。)

    *   **NRZ-I (Non-Return-to-Zero, Invert on Ones) (不归零反向码):**
        *   **Description (描述):** A 1 is represented by an inversion (change) in the signal level, and a 0 is represented by no change. (1 由信号电平的反转（变化）表示，0 由无变化表示。)
        *   **Pros (优点):** Better self-synchronization than NRZ-L (for 1s), less prone to errors from polarity reversal. (比 NRZ-L 具有更好的自同步能力（对于 1），不易受极性反转错误的影响。)
        *   **Cons (缺点):** Still has a DC component, long sequences of 0s can still cause synchronization issues. (仍然存在直流分量，长串的 0 仍然会导致同步问题。)

    *   **RZ (Return-to-Zero) (归零码):**
        *   **Description (描述):** A 1 is represented by a positive pulse that returns to zero in the middle of the bit interval. A 0 is represented by a negative pulse that returns to zero in the middle of the bit interval (or a zero voltage for 0). (1 由在比特间隔中间返回零的正脉冲表示。0 由在比特间隔中间返回零的负脉冲表示（或 0 电压表示 0）。)
        *   **Pros (优点):** Provides self-synchronization (due to transitions in each bit). (提供自同步（由于每个比特中的转换）。)
        *   **Cons (缺点):** Requires twice the bandwidth of NRZ, more complex. (需要 NRZ 两倍的带宽，更复杂。)

    *   **Manchester Encoding (曼彻斯特编码):**
        *   **Description (描述):):** Each bit interval has a transition in the middle. A 0 is represented by a transition from high to low, and a 1 is represented by a transition from low to high. (每个比特间隔中间都有一个转换。0 由从高到低的转换表示，1 由从低到高的转换表示。)
        *   **Pros (优点):** Excellent self-synchronization (a transition in the middle of every bit), no DC component. (出色的自同步能力（每个比特中间都有一个转换），无直流分量。)
        *   **Cons (缺点):** Requires twice the bandwidth of NRZ. (需要 NRZ 两倍的带宽。)

    *   **Unipolar Encoding (单极性编码):**
        *   **Description (描述):** Uses only one polarity (e.g., positive voltage) to represent bits. Typically, a positive voltage represents a 1, and zero voltage represents a 0. (只使用一种极性（例如，正电压）来表示比特。通常，正电压表示 1，零电压表示 0。)
        *   **Pros (优点):** Simple to implement.
        *   **Cons (缺点):** Has a DC component, no self-synchronization (long sequences of 0s or 1s).

    *   **Bipolar AMI (Alternate Mark Inversion) Encoding (双极性 AMI 编码):**
        *   **Description (描述):** A 0 is represented by no line signal. A 1 is represented by alternating positive and negative pulses. The first 1 is represented by a positive pulse, the second by a negative, the third by a positive, and so on. (0 由无线路信号表示。1 由交替的正负脉冲表示。第一个 1 由正脉冲表示，第二个由负脉冲表示，第三个由正脉冲表示，依此类推。)
        *   **Pros (优点):** No DC component, some self-synchronization (due to alternating 1s).
        *   **Cons (缺点):** Long sequences of 0s can cause synchronization issues.

### Self-Synchronization in Digital Signal Transmission (数字信号传输中的自同步)

*   **Importance (重要性):**
    *   **Clock Recovery (时钟恢复):** For the receiver to correctly interpret the incoming bit stream, its clock must be precisely synchronized with the sender's clock. Without synchronization, the receiver might sample the signal at the wrong time, leading to incorrect bit interpretation (e.g., reading a 0 as a 1 or vice versa). (为了让接收方正确解释传入的比特流，其时钟必须与发送方的时钟精确同步。如果不同步，接收方可能会在错误的时间采样信号，导致比特解释错误（例如，将 0 读取为 1，反之亦然）。)
    *   **Bit Delineation (比特定界):** Synchronization helps the receiver determine the start and end of each bit interval, ensuring that each bit is read correctly. (同步有助于接收方确定每个比特间隔的开始和结束，确保每个比特都被正确读取。)
    *   **Preventing Clock Drift (防止时钟漂移):** Over time, small differences in clock speeds between sender and receiver can lead to "clock drift." Self-synchronizing codes embed clock information within the data stream, allowing the receiver to continuously adjust its clock and prevent drift. (随着时间的推移，发送方和接收方之间时钟速度的微小差异会导致“时钟漂移”。自同步编码将时钟信息嵌入到数据流中，允许接收方不断调整其时钟并防止漂移。)

*   **How it works (工作原理):** Self-synchronizing codes achieve this by ensuring there is a sufficient number of signal transitions within the data stream. Each transition allows the receiver to "resynchronize" its clock. (自同步编码通过确保数据流中有足够数量的信号转换来实现这一点。每个转换都允许接收方“重新同步”其时钟。)

*   **Diagram (图示):** (Note: A diagram would typically show the signal transitions for different encoding schemes, illustrating how the receiver's clock can align with these transitions. For example, Manchester encoding has a transition in the middle of every bit, making it highly self-synchronizing.) (注意：图示通常会显示不同编码方案的信号转换，说明接收方的时钟如何与这些转换对齐。例如，曼彻斯特编码在每个比特的中间都有一个转换，使其具有高度的自同步性。)

### Digital-to-Analog Conversion (Modulation) (数字到模拟转换 - 调制)

*   **Purpose (目的):** To convert digital data into analog signals suitable for transmission over analog channels. (将数字数据转换为适合在模拟信道上传输的模拟信号。)
    *  ** ASK-amplitude 1M
      ![image](https://github.com/user-attachments/assets/58d7d711-e7b7-4097-a824-c8d9614de09c)

    *  ** FSK-frequency1M
    ![image](https://github.com/user-attachments/assets/631e7883-1d1b-4dcd-8933-e8364485166a)

    *  ** PSK-Phase1M
    ![image](https://github.com/user-attachments/assets/c7d1f02f-c9b4-4639-b10c-31a1a3f6d870)

      
*   **QAM (Quadrature Amplitude Modulation - 正交幅度调制):**
    *   **Description (描述):** QAM 是一种结合了 ASK 和 PSK 的调制技术，通过同时改变载波的幅度和相位来表示数据。这使得每个符号可以携带更多的比特，从而提高数据传输效率。
    *   **Constellation Diagram (星座图):**
        *   **Definition (定义):** 星座图是一个二维散点图，用于表示数字调制方案中信号的幅度和相位。图中的每个点代表一个可能的信号单元（符号），其在水平轴上的位置表示同相分量 (I)，在垂直轴上的位置表示正交分量 (Q)。
        *   **How to Draw (如何绘制):**
            1.  **确定符号数量 (M):** 对于 M-QAM，有 M 个可能的符号。每个符号携带 `log₂(M)` 比特。
            2.  **映射比特到符号 (Bit-to-Symbol Mapping):** 定义每个比特组合（例如，对于 4-QAM，00, 01, 10, 11）对应的星座点。
            3.  **绘制坐标轴:** 绘制 I (同相) 和 Q (正交) 坐标轴。
            4.  **绘制星座点:** 根据每个符号的幅度和相位（或 I/Q 分量）在图上绘制对应的点。
        *   **Example (示例 - 4-QAM):**
            *   **比特映射:**
                *   00 -> (-1, -1)
                *   01 -> (-1, 1)
                *   10 -> (1, -1)
                *   11 -> (1, 1)
            *   **图示:** 四个点分别位于四个象限，形成一个正方形。
        *   **Example (示例 - 8-QAM):**
            *   **比特映射:** 8-QAM 每个符号携带 3 比特。通常有两组幅度，每组有 4 个相位。例如，内圈 4 个点，外圈 4 个点。
            *   **图示:** 8 个点，通常排列成两个同心正方形或一个八边形。

---

## 8. Signal & Data Rate Calculations (信号与数据速率计算)


### Signal Properties (信号属性)

*   **Relationship between Frequency and Period (频率与周期的关系)**
    *   **Formula (公式):** `f = 1 / T`
    *   **Explanation (解释):** `f` = Frequency (Hz), `T` = Period (s).

### Bandwidth (带宽)

*   **Bandwidth of a Channel (信道带宽)**
    *   **Formula (公式):** `B = f_high - f_low`
    *   **Explanation (解释):** `B` = Bandwidth (Hz), `f_high` = Highest frequency, `f_low` = Lowest frequency.

### Data Rate & Channel Capacity (数据速率与信道容量)

*   **Nyquist Theorem (Noiseless Channel) (奈奎斯特定理 - 无噪声信道)**
    *   **Formula (公式):** `BitRate = 2 * B * log₂(L)`
    *   **Explanation (解释):** `BitRate` (bps), `B` = Bandwidth (Hz), `L` = Number of signal levels.

*   **Shannon's Theorem (Noisy Channel) (香农定理 - 有噪声信道)**
    *   **Formula (公式):** `Capacity = B * log₂(1 + SNR)`
    *   **Explanation (解释):** `Capacity` (bps), `B` = Bandwidth (Hz), `SNR` = Signal-to-Noise Ratio.

*   **Signal-to-Noise Ratio (SNR) (信噪比)**
    *   **Ratio Formula (比率公式):** `SNR = Signal Power / Noise Power`
    *   **Decibel Formula (分贝公式):** `SNR_dB = 10 * log₁₀(SNR)`
    *   **Conversion (转换):** `SNR = 10^(SNR_dB / 10)`

---

## 9. Multiplexing (多路复用)

*   **Multiplexing:** A technique to combine multiple signals into one signal over a shared medium, to make efficient use of a communication channel.
    *   **多路复用:** 将多个信号组合成一个信号并通过共享介质传输的技术，以有效利用通信信道。
*   **Types of Multiplexing:**
    *   **多路复用类型:**
        *   **FDM (Frequency-Division Multiplexing):** Divides the channel's bandwidth into separate frequency bands. Used in analog signals like radio and cable TV.
            *   **频分多路复用 (FDM):** 将信道带宽划分为不同的频段。用于模拟信号，如收音机和有线电视。
        *   **TDM (Time-Division Multiplexing):** Assigns a specific time slot to each signal in a round-robin fashion. Used in digital signals, like the E1/T1 telephone lines.
            *   **时分多路复用 (TDM):** 以轮询方式为每个信号分配一个特定的时间片。用于数字信号，如 E1/T1 电话线。
        *   **WDM (Wavelength-Division Multiplexing):** Used in fiber optics. It multiplexes multiple optical carrier signals onto a single optical fiber by using different wavelengths (colors) of laser light.
            *   **波分多路复用 (WDM):):** 用于光纤通信。通过使用不同波长 (颜色) 的激光，将多个光载波信号复用到单根光纤上。

### Multiplexing Calculations & Concepts (多路复用计算与概念)

*   **Number of TV Channels (电视信道数):** In FDM, the number of TV channels that can be multiplexed depends on the total available bandwidth and the bandwidth required per TV channel. (在 FDM 中，可以复用的电视信道数量取决于总可用带宽和每个电视信道所需的带宽。)

*   **TDM Frame Structure (TDM 帧结构):**
    *   **Number of Available Data Channels (可用数据信道数):** 指的是可以被多路复用的输入源的数量。
    *   **Number of Bits per Frame (每帧比特数):** 在 TDM 中，一帧包含来自所有输入信道的数据。如果每个信道在每帧中贡献 `n` 比特，且有 `C` 个信道，则每帧的总比特数为 `n * C`。
    *   **Serial Data Rate (串行数据率 / 链路比特率):** 这是多路复用链路的总传输速率。它等于帧率乘以每帧的比特数。`Serial Data Rate = Frame Rate * (Bits per Frame)`。
    *   **Frame Rate (帧率):** 每秒传输的帧数。如果每个输入信道的数据速率为 `R_in`，每个时隙的比特数为 `n_slot`，则帧率通常为 `R_in / n_slot`。

*   **Example (示例 - 结合 Question 2c 模拟题):**
    *   **Scenario:** 20 个数字源，每个 1 Mbps，使用 4 比特的时隙进行同步 TDM。
    *   **1. Frame Rate (帧率):**
        *   每个源每秒的比特数 = 1,000,000 bps。
        *   每个时隙的比特数 = 4 比特。
        *   每个源每秒需要的时隙数 = 1,000,000 / 4 = 250,000 时隙/秒。
        *   由于是同步 TDM，帧率 = 每个源每秒需要的时隙数 = 250,000 帧/秒。
    *   **2. Bit Rate (比特率 / 链路比特率):**
        *   每帧的比特数 = 20 个源 * 4 比特/时隙 = 80 比特/帧。
        *   链路比特率 = 帧率 * 每帧的比特数 = 250,000 帧/秒 * 80 比特/帧 = 20,000,000 bps = 20 Mbps。

---

---

## 10. Practice Questions (练习题)

1.  **Define Wi-Fi and list four benefits.**
    *   **定义 Wi-Fi 并列出其四个优点。**
    *   *Answer Hint: Benefits include Convenience, Mobility, Productivity, and easy Deployment.* (答案提示：优点包括便利性、移动性、生产力、易于部署等。)

2.  **You are setting up a Wi-Fi network for a public library with a moderate number of users. Recommend a suitable IEEE 802.11 standard, explaining your choice in terms of frequency, range, and bandwidth. Identify two challenges of deploying WLAN in public spaces and suggest how to overcome them.**
    *   **您需要为一个拥有中等用户数量的公共图书馆建立 Wi-Fi 网络。请推荐一个合适的 IEEE 802.11 标准，并从频率、范围和带宽方面解释您的选择。指出在公共场所部署 WLAN 的两个挑战，并提出克服方法。**
    *   *Answer Hint: Recommend 802.11ax (Wi-Fi 6) for its efficiency in handling multiple devices. Challenges include security (solution: WPA3, captive portal) and interference (solution: channel planning, using 5 GHz band).* (答案提示：推荐 802.11ax (Wi-Fi 6)，因为它能高效处理多设备。挑战包括安全问题（解决方案：WPA3、强制门户认证）和干扰问题（解决方案：信道规划、使用 5 GHz 频段）。)

3.  **A noiseless channel has a bandwidth of 3000 Hz and uses 4 signal levels. What is the maximum bit rate?**
    *   **一个无噪声信道的带宽为 3000 Hz，使用 4 个信号电平。其最大比特率是多少？**
    *   *Solution: Use Nyquist Theorem. BitRate = 2 * 3000 * log₂(4) = 6000 * 2 = 12,000 bps or 12 kbps.*

4.  **We need to send 265 kbps over a noisy channel with a bandwidth of 20 kHz. What is the minimum SNR (in dB) required?**
    *   **我们需要在一个带宽为 20 kHz 的有噪声信道上传输 265 kbps 的数据。所需的最小信噪比 (dB) 是多少？**
    *   *Solution: Use Shannon's Theorem. 265000 = 20000 * log₂(1 + SNR) -> log₂(1 + SNR) = 13.25 -> 1 + SNR = 2¹³·²⁵ -> SNR ≈ 9962. SNR_dB = 10 * log₁₀(9962) ≈ 40 dB.*

---

## 11. Analog Modulation (模拟调制)

*   **Purpose (目的):** To convert digital data into analog signals for transmission over an analog channel, or to shift the frequency of an analog signal for transmission.
    *   **目的:** 将数字数据转换为模拟信号，以便通过模拟信道传输，或改变模拟信号的频率以进行传输。

### Types of Analog Modulation (模拟调制类型)

*   **AM (Amplitude Modulation - 幅度调制):**
    *   **Description (描述):** 载波信号的幅度随基带信号（消息信号）的幅度变化而变化，而载波的频率和相位保持不变。
    *   **Bandwidth (带宽):** `B_AM = 2 * B_m` (其中 `B_m` 是消息信号的带宽)。
    *   **Applications (应用):** 广播电台 (AM Radio)。

*   **FM (Frequency Modulation - 频率调制):**
    *   **Description (描述):** 载波信号的频率随基带信号（消息信号）的幅度变化而变化，而载波的幅度和相位保持不变。
    *   **Bandwidth (带宽):** `B_FM = 2 * (Δf + B_m)` (Carson's Rule - 卡森法则，其中 `Δf` 是最大频率偏移，`B_m` 是消息信号的带宽)。
    *   **Applications (应用):** 广播电台 (FM Radio)，电视伴音。

---

