
# Chapter 8: Data Acquisition - Revision Notes

## Part 1: The Goal & Core Principle (目标与核心原则)

*   **What is Data Acquisition? (什么是数据获取?)**
    *   It is the process of creating a **forensically sound copy** of digital evidence without altering the original source.
    *   它是指在**不改变原始证据**的前提下，创建一个**法证级别的副本**的过程。这个副本通常被称为 **"forensic image" (法证镜像)**。

*   **The Core Principle: Integrity (核心原则：完整性)**
    *   You must prove that the copy you made is an **exact, bit-for-bit duplicate** of the original. Any changes to the original evidence can make it inadmissible in court.
    *   你必须证明你制作的副本与原始证据是**完全一致的、逐个比特精确复制**的。对原始证据的任何改动都可能导致其在法庭上不被采纳。
    *   **How to ensure this? (如何保证？)**
        *   **Write-Blocker (写保护器):** A hardware or software tool that prevents any data from being written to the evidence drive. **This is mandatory.**
        *   **Validation (验证):** Using hashing algorithms to verify integrity.

---

## Part 2: Types of Data Acquisition (数据获取的类型)

*   **1. Static vs. Live Acquisition (静态获取 vs. 动态获取/活体取证)**
    *   **Static Acquisition:** The preferred method. The suspect computer is **powered off**, and the storage device is removed. This is for acquiring **non-volatile data** (永久性数据).
    *   **Live Acquisition:** Performed when a computer **cannot be turned off** (e.g., running server, encrypted disk). It involves capturing **volatile data** like RAM.

*   **2. Four Main Methods of Acquisition (四种主要获取方法)**

| Method (方法) | Description (描述) | When to Use (使用场景) |
| :--- | :--- | :--- |
| **Bit-stream disk-to-image file** | Creates a bit-for-bit, identical copy of the entire source drive and saves it as a file. | **Most common and preferred method.** |
| **Bit-stream disk-to-disk** | Creates a bit-for-bit copy from one physical disk directly to another. | When you don't have enough space for an image file. |
| **Logical Acquisition** | Only copies specific files or folders. Does **not** copy unallocated space. | When time is limited or you are only interested in specific data. |
| **Sparse Acquisition** | Copies specific files/folders and also collects data fragments from **unallocated space**. | More thorough than logical acquisition; can recover deleted data. |

---

## Part 3: Validation - Proving Integrity (验证 - 证明完整性)

**This is the cornerstone of digital forensics.**

*   **What is Hashing? (什么是哈希?)**
    *   An algorithm that produces a unique, fixed-length **hash value** (or "digital fingerprint") from an input. If one bit changes, the hash changes completely.

*   **Common Algorithms (常用算法):**
    *   **MD5:** Older, faster, but has known weaknesses.
    *   **SHA-1, SHA-256, SHA-512:** Secure Hash Algorithm family. **SHA-256 or higher is the current standard.**

*   **The Validation Process (验证流程):**
    1.  **Hash** the original evidence drive.
    2.  **Create** the forensic image.
    3.  **Hash** the forensic image file.
    4.  **Compare** the two hash values. They **MUST** be identical.

---

## Part 4: Acquisition Tools (获取工具)

*   **Linux Command-Line Tools:**
    *   **`dd`:** The traditional tool. Powerful but lacks forensic features.
    *   **`dcfldd`:** **The preferred command-line tool.** An enhanced `dd` for forensics.
        *   **Key Advantages:** On-the-fly hashing (`hash=...`), progress bar (`status=on`), error logging (`errlog=...`), and verification (`vf=...`).

*   **GUI Tools (图形界面工具):**
    *   **FTK Imager, EnCase Forensic Imager, ProDiscover:** Industry-standard commercial tools.
    *   **Advantages:** User-friendly, integrated hashing, support for various image formats (e.g., `.E01`), and automatic handling of different file systems.

---

## Part 5: Special Considerations (特殊情况)

*   **RAID (Redundant Array of Independent Disks):**
    *   **The Challenge:** Data is spread across multiple disks. You must acquire **all disks** in the array and use a tool that can reconstruct the original volume.

*   **Remote Acquisition (远程获取):**
    *   **When:** When physical access is not possible (e.g., network servers).
    *   **How:** Uses a remote agent on the suspect machine to send data over the network.
    *   **Drawbacks:** Slow, requires permissions, and alters the suspect system.
