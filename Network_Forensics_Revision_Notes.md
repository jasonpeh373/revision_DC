
# Chapter 11: Network Forensics - Revision Notes

## Part 1: What is Network Forensics & Why is it Hard?

*   **What is it? (定义)**
    *   **In English:** Network Forensics is the process of capturing, recording, and analyzing network traffic and event logs to investigate security incidents or malicious activities.
    *   **中文解释:** 网络取证是指通过**捕获、记录和分析网络流量及事件日志**，来调查安全事件（如黑客攻击）的过程，目的是找出攻击者、其行为及方式。

*   **Key Goals (主要目标):**
    *   Identify the source of an attack (找到攻击源头).
    *   Determine the extent of the intrusion (搞清楚影响范围).
    *   Reconstruct the attacker's actions (重现攻击者的行为).
    *   Gather evidence for legal proceedings (为法律程序收集证据).

*   **Challenges (主要难点):**
    *   **Volatility (易失性):** Network traffic is transient. If you don't record it as it happens, it's gone forever.
    *   **Volume (数据量大):** Busy networks generate enormous amounts of data, making storage and analysis difficult.
    *   **Encryption (加密):** Encrypted traffic (e.g., HTTPS) hides the content, making it impossible to see *what* was communicated, only *who* was communicating.

---

## Part 2: Where to Find Evidence? (证据在哪里？)

Network evidence primarily comes from two sources: **Live Traffic** and **Logs**.

| Evidence Source (证据来源) | Description (描述) | Pros (优点) | Cons (缺点) |
| :--- | :--- | :--- | :--- |
| **Packet Captures (数据包捕获)** | Capturing actual data packets (`.pcap` files). | **Most detailed evidence.** You can see everything (if not encrypted). | Requires huge storage; can be overwhelming to analyze. |
| **Firewall Logs (防火墙日志)** | Records connections that were allowed or blocked. | Good for seeing scans, unauthorized access attempts. | Doesn't show the *content* of the traffic. |
| **IDS/IPS Logs** | Intrusion Detection/Prevention System logs. | **Highlights potential attacks** for you. | Can have false positives; might miss new types of attacks. |
| **Router/Switch Logs** | Records device activity and MAC/IP address mappings. | Useful for tracking a device's physical location on the network. | Often have limited storage and get overwritten quickly. |
| **Server Logs** | Web, database, or authentication server logs. | Shows user activity, login attempts, commands run. | Only shows what happened on that specific server. |

---

## Part 3: The Ultimate Tool - Wireshark

Wireshark is the core tool for analyzing `.pcap` files.

*   **Key Features for Forensics:**
    *   **Display Filters (显示过滤器):** The most powerful feature for finding specific traffic.
        *   `ip.addr == 192.168.1.100`: Show all packets to or from this IP.
        *   `tcp.port == 80`: Show all HTTP traffic.
        *   `http.request`: Show only HTTP requests (e.g., GET, POST).
    *   **Follow TCP Stream (追踪TCP流):** Reassembles a TCP conversation to show the full data exchanged. Incredibly useful for unencrypted protocols like HTTP, FTP, Telnet.
    *   **Statistics Menu (统计菜单):**
        *   `Statistics > Conversations`: Shows who is talking to whom and how much data they've sent.
        *   `Statistics > Protocol Hierarchy`: Shows a breakdown of all protocols in the capture.
        *   `Statistics > Endpoints`: Lists all IP and MAC addresses seen in the capture.

---

## Part 4: Analyzing Common Protocols

*   **HTTP (Hypertext Transfer Protocol):**
    *   **What to look for:** Usernames, passwords, session cookies (if in cleartext), visited URLs, downloaded files, User-Agent string (browser info).

*   **DNS (Domain Name System):**
    *   **What to look for:** DNS queries can reveal which websites a user visited or which command-and-control (C2) server malware tried to contact.

*   **FTP (File Transfer Protocol):**
    *   **What to look for:** Usernames and passwords are sent in **cleartext**. You can also see which files were uploaded or downloaded.

*   **TCP (Transmission Control Protocol):**
    *   **What to look for:**
        *   **Port Scanning:** A large number of `SYN` packets sent to many different ports on a target, without completing the handshake, indicates a **port scan**.
        *   **Unusual Flags:** `RST` (Reset) flags can indicate forcefully closed connections, often related to scanning.

---

## How to Answer Exam Questions

**Q1: What are the main challenges in network forensics? Explain one.**

*   **Answer:** The main challenges are data **volatility**, high **volume**, and **encryption**.
    *   **Volatility** means that network data is transient and is lost if not captured in real-time. Unlike data on a hard drive, network traffic exists only for a moment. If an investigator does not have a system in place to continuously record traffic, crucial evidence of an attack will be gone forever.

**Q2: You are given a `.pcap` file to investigate potential data theft. What are the first three things you would do in Wireshark?**

*   **Answer:**
    1.  **Check Protocol Hierarchy:** Go to `Statistics > Protocol Hierarchy` to get an overview. Look for unusually high amounts of traffic for protocols like FTP or SMB (file sharing).
    2.  **Analyze Conversations:** Go to `Statistics > Conversations` and sort by byte count. This helps identify which internal host sent the most data to an external IP.
    3.  **Filter and Follow Streams:** Apply a display filter for the suspicious IP (e.g., `ip.addr == [suspicious_IP]`). Then, right-click a packet and select `Follow > TCP Stream` to reconstruct the data transfer and see what was sent (if unencrypted).

**Q3: An IDS log shows a "Port Scan" alert from IP `1.2.3.4` against your server `10.0.0.5`. How would you use a packet capture to verify this?**

*   **Answer:**
    *   In Wireshark, I would apply the display filter: `ip.src == 1.2.3.4 and ip.dst == 10.0.0.5 and tcp.flags.syn == 1 and tcp.flags.ack == 0`.
    *   This filter isolates initial TCP handshake packets (`SYN` packets) from the attacker to the server.
    *   If I see a large number of these packets sent to many different destination ports on my server in a short period, without corresponding `SYN-ACK` replies to complete the handshake, it confirms that a SYN scan took place.
