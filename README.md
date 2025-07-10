# Software Engineering Exam Revision Notes (软件工程考试复习笔记)

---

## Topic 1: Software Architecture (软件架构)

#### 1. What is software design? (什么是软件设计?)

 **As per your correction:**
 "The process of defining the software architecture, components, modules, interfaces, and data for a software system to satisfy specified requirements."

 **中文翻译 (Chinese Translation):**
 “为了满足指定的需求，而定义软件系统的软件架构、组件、模块、接口和数据的过程。”

#### 2. Describe the software design process. (描述软件设计过程)

 **From your notes (Lecture 7 & 8, Slide 9):**
 * Architectural design - Identify sub-systems
 * Abstract specification - Specify sub-systems
 * Interface design - Describe sub-system interfaces
 * Component design - Decompose sub-systems into components
 * Data structure design - Design data structures to solve data problem
 * Algorithm design - Design algorithms to solve functionalities problems

 **中文翻译 (Chinese Translation):**
 * 架构设计: 识别子系统。
 * 抽象规格说明: 为子系统制定规格。
 * 接口设计: 描述子系统的接口。
 * 组件设计: 将子系统分解为组件。
 * 数据结构设计: 设计用于解决数据问题的数据结构。
 * 算法设计: 设计用于解决功能问题的算法。

#### 3. What is software architecture? (什么是软件架构?)

 **As per your correction:**
 "The architecture of a system is a comprehensive framework that describes its form and structure - its components and how they fit together."

 **中文翻译 (Chinese Translation):**
 “一个系统的架构是一个全面的框架，它描述了系统的形式和结构——即它的组件以及它们如何组合在一起。”

#### 4. Describe the architectural model. (描述架构模型)

 **From your notes (Lecture 7 & 8, Slide 18):**
 The architectural model consists of:
 *   **Structural Model**
     *   Repository Model
     *   Client Server Model
     *   Abstract Machine (Layered) Model
 *   **Control Model**
     *   Centralized Model
     *   Event-Driven Model
 *   **Decomposition Model**
     *   Object Model
     *   Pipelining Model

 **中文翻译 (Chinese Translation):**
 架构模型包含：
 *   **结构模型**
     *   仓库模型
     *   客户端-服务器模型
     *   抽象机 (分层) 模型
 *   **控制模型**
     *   集中式模型
     *   事件驱动模型
 *   **分解模型**
     *   对象模型
     *   管道模型

#### 5. Describe the structural model (Architectural Styles) and list the advantages and disadvantages of each model. (描述结构模型 (架构风格) 并列出优缺点)

 **From your notes (Lecture 7 & 8, Slide 18):**
 The "Structural Model" section on this slide lists three main types. We will detail each one based on the subsequent slides in your notes.

 **中文翻译 (Chinese Translation):**
 此幻灯片上的“结构模型”部分列出了三种主要类型。我们将根据你笔记中后续的幻灯片来详细说明每一种。

**a) Repository Model (仓库模型)**

 **From your notes (Slide 19, 21):**
 *   **Description:** "Shared data is held in a central database or repository and may be accessed by all sub-systems." It is used when sub-systems must exchange large amounts of data.
 *   **Advantages:**
     *   "Efficient way to share large amounts of data."
     *   "Sub-systems need not be concerned with how data is produced."
     *   "Centralised management e.g. backup, security, etc."
 *   **Disadvantages:**
     *   "Sub-systems must agree on a repository data model. Inevitably a compromise."
     *   "Data evolution is difficult and expensive."
     *   "Difficult to distribute efficiently."

 **中文翻译 (Chinese Translation):**
 *   **描述:** “共享数据保存在中央数据库或仓库中，所有子系统都可以访问。” 当子系统间必须交换大量数据时使用。
 *   **优点:**
     *   “共享大量数据的高效方式。”
     *   “子系统无需关心数据是如何生产的。”
     *   “集中式管理，例如备份、安全等。”
 *   **缺点:**
     *   “子系统必须就仓库数据模型达成一致。这不可避免地是一种妥协。”
     *   “数据演变困难且昂贵。”
     *   “难以高效地进行分发。”

**b) Client-Server Model (客户端-服务器模型)**

 **From your notes (Slide 22, 24):**
 *   **Description:** "Distributed system model which shows how data and processing is distributed across a range of components. Set of stand-alone servers which provide specific services."
 *   **Advantages:**
     *   "Distribution of data is straightforward."
     *   "Makes effective use of networked systems."
     *   "Easy to add new servers or upgrade existing servers."
 *   **Disadvantages:**
     *   "No shared data model so sub-systems use different data organisation. Data interchange may be inefficient."
     *   "Redundant management in each server."
     *   "No central register of names and services - it may be hard to find out what servers and services are available."

 **中文翻译 (Chinese Translation):**
 *   **描述:** “一种分布式系统模型，展示了数据和处理如何在一系列组件中分布。由一组提供特定服务的独立服务器构成。”
 *   **优点:**
     *   “数据分发是直接了当的。”
     *   “有效利用网络化系统。”
     *   “易于添加新服务器或升级现有服务器。”
 *   **缺点:**
     *   “没有共享的数据模型，因此子系统使用不同的数据组织。数据交换可能效率低下。”
     *   “每个服务器中都有冗余的管理。”
     *   “没有名称和服务的中央注册表——因此可能很难发现有哪些可用的服务器和服务。”

**c) Abstract Machine (Layered) Model (抽象机/分层模型)**

> **From your notes (Slide 25):**
> *   **Description:** "Organises the system into a set of layers (or abstract machines) each of which provide a set of services."
> *   **Advantages (inferred from description):**
>     *   "Supports the incremental development of sub-systems in different layers."
>     *   "When a layer interface changes, only the adjacent layer is affected." (This implies good maintainability).
> *   **Disadvantages:**
>     *   "However, often artificial to structure systems in this way."
>
> **中文翻译 (Chinese Translation):**
> *   **描述:** “将系统组织成一组层次（或抽象机），每个层次都提供一组服务。”
> *   **优点 (从描述中推断):**
>     *   “支持在不同层次中增量式地开发子系统。”
>     *   “当一个层的接口改变时，只有相邻的层会受到影响。” (这意味着良好的可维护性)。
> *   **缺点:**
>     *   “然而，用这种方式来构建系统通常会显得不自然。”

#### 6. Describe the control model. (描述控制模型)

> **From your notes (Slide 18, 27, 28):**
> The "Control Model" is concerned with the control flow between sub-systems. There are two main styles:
> 1.  **Centralised Control:** "One sub-system has overall responsibility for control and starts and stops other sub-systems." This can be further divided into:
>     *   **Call-return model:** "Top-down subroutine model where control starts at the top of a subroutine hierarchy and moves downwards."
>     *   **Manager model:** "One system component controls the stopping, starting and coordination of other system processes."
> 2.  **Event-Based Control:** "Each sub-system can respond to externally generated events from other sub-systems or the system's environment."
>
> **中文翻译 (Chinese Translation):**
> “控制模型”关注子系统之间的控制流。主要有两种风格：
> 1.  **集中式控制:** “一个子系统全面负责控制，并启动和停止其他子系统。” 这可以进一步分为：
>     *   **调用-返回模型:** “自上而下的子程序模型，其中控制从子程序层次结构的顶部开始并向下移动。”
>     *   **管理者模型:** “一个系统组件控制其他系统进程的停止、启动和协调。”
> 2.  **基于事件的控制:** “每个子系统都可以响应来自其他子系统或系统环境的外部生成事件。”

---

## Topic 2: Software Testing (软件测试) - SKIPPED
### 1. What is V&V? (什么是 V&V？)
*   **V&V** stands for **Verification and Validation**.
    *   **中文解释:** V&V 指的是 **验证 (Verification)** 和 **确认 (Validation)**。
*   It is a system engineering discipline to assess the correctness and quality of software throughout its life cycle.
    *   **中文解释:** 它是一个系统工程的准则，用来在整个软件生命周期中，评估和检测软件的正确性与质量。
*   **Verification:** "Are we building the product right?". It ensures the software conforms to its specifications.
    *   **中文解释 (验证):** 关注的是 **“我们是否在正确地构建产品？”**。它确保软件符合其设计规格和标准。
*   **Validation:** "Are we building the right product?". It ensures the software meets the user's real needs.
    *   **中文解释 (确认):** 关注的是 **“我们是否在构建正确的产品？”**。它确保软件满足用户的真实需求。
*(参考幻灯片第3、4页)*

### 2. How to perform V&V? (如何执行 V&V？)
V&V is performed through two complementary activities:
*   **Software Inspection (Static Analysis):**
    *   This is a **static** method that does not require program execution. It analyzes static representations (documents, code) to find problems.
    *   **中文解释 (软件审查/静态分析):** 这是一种 **静态** 的方法，不需要运行程序。它通过分析和检查系统的静态表示（如文档、图表、源代码）来发现问题。
*   **Software Testing (Dynamic Analysis):**
    *   This is a **dynamic** method that requires program execution. It observes the software's behavior with test data to find defects.
    *   **中文解释 (软件测试/动态分析):** 这是一种 **动态** 的方法，需要实际运行程序。它通过执行软件，输入测试数据，并观察其行为来发现缺陷。
*(参考幻灯片第7页)*

### 3. Describe about software inspection and its processes. (描述软件审查及其过程)
*   **Software Inspection** is a formal technique to find errors, omissions, and anomalies in any system representation without executing it.
    *   **中文解释 (软件审查):** 是一种正式的技术，旨在发现系统任何表示形式（文档、模型、代码等）中的错误、遗漏和异常，并且 **不需要执行系统**。
*   **The Inspection Process** includes several stages:
    1.  **Planning:** Prepare materials and team.
    2.  **Overview:** Introduce the background and goals to the team.
    3.  **Individual Preparation:** Team members review materials independently.
    4.  **Inspection Meeting:** The team discusses and records findings.
    5.  **Rework:** The author fixes the identified defects.
    6.  **Follow-up:** Verify that all defects have been corrected.
    *   **中文解释 (审查过程):** 1. **计划** -> 2. **概述** -> 3. **个人准备** -> 4. **审查会议** -> 5. **返工** -> 6. **跟进**。
*(参考幻灯片第8、11页)*

### 4. How to perform inspection? (如何执行审查？)
1.  Present a system overview to the team.
2.  Distribute code and documents in advance.
3.  Conduct the inspection meeting and note all discovered errors.
4.  Make modifications to repair the errors.
5.  Re-inspection may be required to verify the fixes.
    *   **中文解释:** 1. **介绍概览** -> 2. **分发文档** -> 3. **开会审查** -> 4. **修复错误** -> 5. **必要时再审查**。
*(参考幻灯片第12页)*

### 5. What is software testing? (什么是软件测试？)
*   It is the process of **analyzing** a software item to **detect** the differences between existing and required conditions (i.e., bugs) and to **evaluate** the features of the software.
    *   **中文解释:** 软件测试是一个 **分析** 软件项的过程，目的是 **发现** 现有状况和需求状况之间的 **差异**（即缺陷/Bugs），并 **评估** 该软件项的功能特性。
*(参考幻灯片第23页)*

### 6. Describe about black-box testing. (描述黑盒测试)
*   **Black-box testing** (or closed box testing) focuses on the **functionality** of the test object, without looking at its internal structure or code.
    *   **中文解释 (黑盒测试):** 也叫封闭盒测试，是一种关注于测试对象 **功能性** 的测试方法。测试人员不关心软件内部的结构和代码，只关心输入什么，系统是否能产生正确的输出。
*(参考幻灯片第24页)*

### 7. List the six basic types of testing. (列出六种基本的测试类型)
1.  **Unit** (单元测试)
2.  **Integration** (集成测试)
3.  **Function/System** (功能/系统测试)
4.  **Acceptance** (验收测试)
5.  **Regression** (回归测试)
6.  **Beta** (Beta测试)
*(参考幻灯片第25页)*

### 8. Describe about component and system testing. (描述组件测试和系统测试)
*   **Component Testing (Unit Testing):**
    *   Tests individual program components. Usually done by the developer. Tests are based on the developer's experience.
    *   **中文解释 (组件测试/单元测试):** 测试独立、单个的程序组件。通常由开发该组件的程序员负责，测试用例主要基于开发者的经验来设计。
*   **System Testing:**
    *   Tests groups of components integrated into a system or sub-system. Usually done by an independent test team. Tests are based on the system specification.
    *   **中文解释 (系统测试):** 测试集成了多个组件后形成的系统或子系统。通常由一个独立的测试团队负责，测试用例主要基于系统的需求规格说明书来设计。
*(参考幻灯片第39页)*

### 9. What is a test case? (什么是测试用例？)
*   A Test Case consists of:
    1.  A set of **inputs**
    2.  Execution **preconditions**
    3.  Expected **outcomes**
*   **中文解释:** 一个测试用例包含三个主要部分：1. **一组输入** -> 2. **执行前置条件** -> 3. **预期的输出结果**。
*(参考幻灯片第40页)*

### 10. Describe about software testing process. (描述软件测试过程)
1.  **Design test cases:** Define inputs and expected outputs.
2.  **Prepare test data:** Create the specific inputs for the test.
3.  **Run program with test data:** Execute the software.
4.  **Compare results to test cases:** Check if the actual output matches the expected output.
    *   **中文解释:** 1. **设计测试用例** -> 2. **准备测试数据** -> 3. **运行程序** -> 4. **比较结果**。
*(参考幻灯片第41页)*

### 11. Describe about the two types of test cases? (描述两种类型的测试用例)
1.  **Positive test case:**
    *   Designed to verify that the program works as expected with **valid inputs**.
    *   **中文解释 (正向测试用例):** 使用 **有效的** 输入来验证程序能够 **成功** 运行的场景。
2.  **Negative test case:**
    *   Designed to verify that the program handles **invalid inputs** gracefully (e.g., shows an error). It tests the program's **robustness**.
    *   **中文解释 (负向测试用例):** 使用 **无效的** 输入来验证程序能够妥善处理错误，用以测试程序的 **健壮性**。
*(参考幻灯片第42页)*

### 12. List the four methods to identify test Case. (列出四种识别测试用例的方法)
1.  **Boundary Value Analysis** (边界值分析)
2.  **Equivalence Partitioning** (等价类划分)
3.  **Logic Coverage** (逻辑覆盖)
4.  **Random Generation** (随机生成)
*(参考幻灯片第43页)*

### 13. Describe about boundary value analysis. (描述边界值分析)
*   **Boundary Value Analysis (BVA)** is a testing technique that focuses on the **boundaries** (or limits) of an input range, as this is where errors most often occur.
    *   **中文解释 (边界值分析):** 是一种专注于测试输入值 **边界** 的技术，因为大多数错误都发生在边界上。
*   Test cases are designed for values that are on, just above, and just below the boundary. For a range of [0, 100], BVA would test values like -1, 0, 1 and 99, 100, 101.
    *   **中文解释 (举例):** 如果一个有效范围是 [0, 100]，BVA会选择像 -1, 0, 1 和 99, 100, 101 这样的值来测试。
*(参考幻灯片第44、45页)*

### 14. System testing contain functional and performance testing. Describe both of the testing. (系统测试包含功能测试和性能测试，描述这两种测试)
*   **Functional Testing:**
    *   Tests the implementation of business needs. It checks if the system does what it is supposed to do according to the requirements.
    *   **中文解释 (功能测试):** 验证系统是否正确地 **实现了业务需求**，即检查系统是否“做对了事”。
*   **Performance Testing:**
    *   Tests non-functional requirements like speed, load, etc.
    *   **中文解释 (性能测试):** 测试系统的 **非功能性需求**，例如速度、负载等。
    *   It includes:
        *   **Load Testing:** Testing with many users at the same time. (负载测试)
        *   **Stress Testing:** Finding the maximum number of users before the system breaks. (压力测试)
        *   **Endurance Testing:** Testing for a long time for reliability. (耐力测试)
        *   **Spike Testing:** Testing sudden stress on the system. (尖峰测试)
---

## Topic 3: Configuration Management (配置管理)

#### 0. What is the Configuration Management Process? (什么是配置管理过程?)
*(This question was added based on your request to focus on the "process".)*

 **From your notes (Lecture 12, Slide 5 & 13):**
 The configuration management process involves four main activities:
 *   **Version management:** Keeping track of the multiple versions of system components and ensuring that changes made to components by different developers do not interfere with each other.
 *   **System building:** The process of assembling program components, data and libraries, then compiling and linking these to create an executable system.
 *   **Change management:** Keeping track of requests for changes to the software from customers and developers, working out the costs and impact of making these changes, and deciding if and when the changes should be implemented.
 *   **Release management:** Preparing software for external release and keeping track of the system versions that have been released for customer use.

 **中文翻译 (Chinese Translation):**
 配置管理过程涉及四个主要活动：
 *   **版本管理:** 跟踪系统组件的多个版本，并确保不同开发人员对组件所做的更改不会相互干扰。
 *   **系统构建:** 组装程序组件、数据和库，然后编译和链接它们以创建可执行系统的过程。
 *   **变更管理:** 跟踪来自客户和开发人员的软件变更请求，计算进行这些变更的成本和影响，并决定是否以及何时实施这些变更。
 *   **发布管理:** 准备要对外发布的软件，并跟踪已发布给客户使用的系统版本。

---

#### 1. What is configuration management? (什么是配置管理?)

 **From your notes (Lecture 12, Slide 4):**
 "General process of managing a changing software system. The aim of CM is to support the system integration process so that all developers can access the project code and documents in a coherent way, and find out what changes have been made."

 **中文翻译 (Chinese Translation):**
 “管理一个不断变化的软件系统的通用过程。配置管理的目标是支持系统集成过程，以便所有开发人员能够以一致的方式访问项目代码和文档，并找出已发生的变更。”

---

#### 2. What are the factors that influence software change? (影响软件变更的因素有哪些?)

 **From your notes (Lecture 10, Slide 6, "What Cause Changes?")**:
 *   **New requirements:** Emerge when the software is used.
 *   **Change of environment:** Need to adapt to the new environment.
 *   **Errors:** Must be repaired.
 *   **New computers and equipment:** Added to the system.
 *   **Performance or reliability:** Require improvement.

 **中文翻译 (Chinese Translation):**
 *   **新的需求:** 在软件使用过程中出现。
 *   **环境的改变:** 需要适应新的环境。
 *   **错误:** 必须被修复。
 *   **新的计算机和设备:** 被添加到系统中。
 *   **性能或可靠性:** 需要改进。

---

#### 3. What is change management? (什么是变更管理?)

 **From your notes (Lecture 12, Slide 13):**
 "Change management is the process of keeping track of requests for changes to the software from customers and developers, working out the costs and impact of making these changes, and deciding if and when the changes should be implemented."

 **中文翻译 (Chinese Translation):**
 “变更管理是这样一个过程：它跟踪来自客户和开发人员的软件变更请求，计算进行这些变更的成本和影响，并决定是否以及何时实施这些变更。”

---

#### 4. Describe configuration item, baseline, release, and version. (描述配置项、基线、发布和版本)

 **Configuration Item (配置项)**
 **From your notes (Lecture 12, Slide 7):**
 "Software Configuration Items are the things that are created as part of the software process. [Examples include] source code, design documents, test data, user manuals."

 **中文翻译 (Chinese Translation):**
 “软件配置项是在软件过程中创建的东西。[例子包括] 源代码、设计文档、测试数据、用户手册。”

 ---
 **Baseline (基线)**
 **From your notes (Lecture 12, Slide 8):**
 "A baseline is a collection of component versions that make up a system. Baselines are controlled which means that versions of the components making up the system cannot be changed."

 **中文翻译 (Chinese Translation):**
 “基线是构成一个系统的组件版本的集合。基线是受控的，这意味着构成系统的组件版本不能被更改。”

 ---
 **Version (版本)**
 **From your notes (Lecture 12, Slide 10):**
 "A version is an instance of a configuration item that differs, in some way, from other instances of that item."

 **中文翻译 (Chinese Translation):**
 “版本是配置项的一个实例，它在某些方面与该项的其他实例有所不同。”

 ---
 **Release (发布)**
 **From your notes (Lecture 12, Slide 15):**
 "A release is a version of a system that is distributed to customers."

 **中文翻译 (Chinese Translation):**
 “发布是分发给客户的一个系统版本。”

---

#### 5. Describe release management. (描述发布管理)

 **From your notes (Lecture 12, Slide 16):**
 "Release management is concerned with the process of deciding which versions of components should be included in a system release, the production and distribution of the release."

 **中文翻译 (Chinese Translation):**
 “发布管理关注的是这样一个过程：决定哪些组件版本应包含在系统发布中，以及该发布的制作和分发。”

---

#### 6. Describe system release. (描述系统发布)

 **From your notes (Lecture 12, Slide 15):**
 "A release is a version of a system that is distributed to customers. Releases may be:
 *   Major releases with new functionality, minor releases that repair bugs and fix customer problems.
 *   Releases for different platforms such as Windows, Linux, etc."

 **中文翻译 (Chinese Translation):**
 “发布是分发给客户的一个系统版本。发布可以是：
 *   带有新功能的主要发布，以及修复错误和解决客户问题的次要发布。
 *   针对不同平台的发布，例如 Windows、Linux 等。”

---

## Topic 4: Quality Management (质量管理)

#### 1. What is software quality management? (什么是软件质量管理?)

 **From your notes (Lecture 11, Slide 4):**
 "Software quality management is concerned with ensuring that the required level of quality is achieved in a software product. It has three main activities:
 *   **Quality assurance:** The definition of processes and standards that should lead to high-quality software.
 *   **Quality planning:** The selection of appropriate processes and standards from the general quality management process.
 *   **Quality control:** The application of processes to ensure that they have been followed and implemented."

 **中文翻译 (Chinese Translation):**
 “软件质量管理关注的是确保软件产品达到所要求的质量水平。它有三个主要活动：
 *   **质量保证 (QA):** 定义能够产出高质量软件的过程和标准。
 *   **质量策划 (QP):** 从通用的质量管理过程中选择适当的过程和标准。
 *   **质量控制 (QC):** 应用过程以确保它们已被遵守和执行。”

---

#### 2. What are software quality attributes? (什么是软件质量属性?)

 **From your notes (Lecture 11, Slide 20):**
 These are the characteristics of software that determine its quality. The specific attributes that are important depend on the application.
 *   Safety
 *   Security
 *   Reliability
 *   Resilience
 *   Robustness
 *   Understandability
 *   Testability
 *   Adaptability
 *   Portability
 *   Usability
 *   Reusability
 *   Efficiency
 *   Learnability

 **中文翻译 (Chinese Translation):**
 这些是决定软件质量的特性。具体哪些属性是重要的，取决于应用程序本身。
 *   安全性 (Safety)
 *   信息安全 (Security)
 *   可靠性 (Reliability)
 *   弹性 (Resilience)
 *   健壮性 (Robustness)
 *   可理解性 (Understandability)
 *   可测试性 (Testability)
 *   适应性 (Adaptability)
 *   可移植性 (Portability)
 *   可用性 (Usability)
 *   可复用性 (Reusability)
 *   效率 (Efficiency)
 *   易学性 (Learnability)

---

#### 3. What is the importance of Quality Assurance? (质量保证的重要性是什么?)

 **From your notes (Lecture 11, Slide 6 and your mind map):**
 The fundamental importance of Quality Assurance (QA) is in "providing confidence that the required quality is achieved." This confidence is critical in several areas:
 *   **Customer Satisfaction:** QA helps a company create products and services that meet or exceed customer needs and expectations.
 *   **Public Trust:** Consistently delivering high-quality products builds a reputation for reliability and earns public trust, which is a valuable business asset.
 *   **Product Quality:** QA involves defining standards and processes (like coding standards and testing procedures) that proactively prevent defects, rather than just finding them later. This leads to a higher quality final product.

 **中文翻译 (Chinese Translation):**
 质量保证 (QA) 的根本重要性在于“提供已达到所要求质量的信心”。这种信心在以下几个方面至关重要：
 *   **客户满意度:** QA 帮助公司创造出满足甚至超越客户需求和期望的产品与服务。
 *   **公众信任:** 持续交付高质量产品能够建立可靠的声誉，赢得公众信任，这是一项宝贵的商业资产。
 *   **产品质量:** QA 涉及定义标准和流程（如编码标准和测试流程），从而主动地预防缺陷，而不仅仅是事后发现它们。这会带来更高质量的最终产品。

---

#### 4. Describe Quality Reviews. (描述质量评审)

 **From your notes (Lecture 11, Slide 13):**
 "A group of people carefully examine part or all of a software system and its associated documentation. The objective of a review is to find defects and inconsistencies in the software and its documentation. The conclusions of the review are formally recorded and passed to the author."

 **中文翻译 (Chinese Translation):**
 “一组人员仔细地检查部分或全部的软件系统及其相关文档。评审的目标是在软件及其文档中发现缺陷和不一致之处。评审的结论会被正式记录下来并递交给作者。”

---

#### 5. Describe ISO 9000. (描述 ISO 9000)

 **From your notes (Lecture 11, Slide 10):**
 "ISO 9000 is an international set of standards for quality management. They can be applied to a range of organisations from manufacturing to service industries. ISO 9001 is the most general of these standards and it applies to organisations that design, develop and maintain products. A supporting document (ISO 9000-3) interprets ISO 9001 for software development."

 **中文翻译 (Chinese Translation):**
 “ISO 9000 是一套关于质量管理的国际标准。它们可以应用于从制造业到服务业的各种组织。ISO 9001 是这些标准中最通用的一个，它适用于那些设计、开发和维护产品的组织。一份支持性文件 (ISO 9000-3) 对 ISO 9001 在软件开发中的应用进行了解释。”

---

## Topic 5: Software Maintenance (软件维护)

#### 1. What is software maintenance? (什么是软件维护?)

 **From your notes (Lecture 10, Slide 7):**
 "The modification of a software product after delivery to correct faults, to improve performance or other attributes, or to adapt the product to a modified environment."

 **中文翻译 (Chinese Translation):**
 “在产品交付后对其进行的修改，以修正错误、提升性能或其他属性，或使产品适应变化了的环境。”

---

#### 2. What are the types of maintenance? (软件维护有哪些类型?)

 **From your notes (Lecture 10, Slide 9):**
 There are three main types of software maintenance:
 *   **Maintenance to repair software faults:** Changing a system to correct deficiencies in the way it meets its requirements. (Often called Corrective Maintenance)
 *   **Maintenance to adapt software to a different operating environment:** Changing a system so that it operates in a different environment (computer, OS, etc.) from its initial implementation. (Often called Adaptive Maintenance)
 *   **Maintenance to add to or modify the system's functionality:** Modifying the system to satisfy new requirements. (Often called Perfective Maintenance)

 **中文翻译 (Chinese Translation):**
 软件维护主要有三种类型：
 *   **修复软件故障的维护:** 改变系统以纠正其满足需求方式中的缺陷。（通常称为纠正性维护）
 *   **使软件适应不同操作环境的维护:** 改变系统，使其能在不同环境（计算机、操作系统等）下运行，而非其最初实现的环境。（通常称为适应性维护）
 *   **增加或修改系统功能的维护:** 修改系统以满足新的需求。（通常称为完善性维护）

#### 3. What are the costs of maintenance? (维护成本有哪些?)

 **From your notes (Lecture 10, Slide 11):**
 *   Usually greater than development costs (2* to 100* depending on the application).
 *   Affected by both technical and non-technical factors.
 *   Increases as software is maintained.
 *   Maintenance corrupts the software structure so makes further maintenance more difficult.
 *   Ageing software can have high support costs (e.g. old languages, compilers etc.).

 **中文翻译 (Chinese Translation):**
 *   通常高于开发成本（根据应用不同，可能是2到100倍）。
 *   受技术和非技术因素影响。
 *   随着软件的维护而增加。
 *   维护会破坏软件结构，使后续维护更加困难。
 *   老化的软件可能产生高昂的支持成本（例如，旧的语言、编译器等）。

#### 4. What are the factors influencing maintenance costs? (影响维护成本的因素有哪些?)

 **From your notes (Lecture 10, Slide 13):**
 *   **Team stability:** Maintenance costs are reduced if the same staff are involved with them for some time.
 *   **Contractual responsibility:** The developers of a system may have no contractual responsibility for maintenance so there is no incentive to design for future change.
 *   **Staff skills:** Maintenance staff are often inexperienced and have limited domain knowledge.
 *   **Program age and structure:** As programs age, their structure is degraded and they become harder to understand and change.

 **中文翻译 (Chinese Translation):**
 *   **团队稳定性:** 如果由同一批人员长期参与维护，维护成本会降低。
 *   **合同责任:** 系统开发者可能没有维护的合同责任，因此没有动力为未来的变更进行设计。
 *   **员工技能:** 维护人员通常经验不足，领域知识有限。
 *   **程序年龄和结构:** 随着程序的老化，其结构会退化，变得更难理解和修改。

#### 5. What is maintenance prediction? (什么是维护预测?)

 **From your notes (Lecture 10, Slide 14):**
 Maintenance prediction is concerned with:
 *   Assessing parts of the system that may cause problems.
 *   Assessing parts of the system that may have high maintenance costs.

 **中文翻译 (Chinese Translation):**
 维护预测关注的是：
 *   评估系统中可能导致问题的部分。
 *   评估系统中可能产生高维护成本的部分。

#### 6. What are the assumptions for maintenance prediction? (维护预测的假设是什么?)

 **From your notes (Lecture 10, Slide 14):**
 Prediction Assumptions:
 *   Change acceptance depends on the maintainability of the components affected by the change.
 *   Implementing changes degrades the system and reduces its maintainability.
 *   Maintenance costs depend on the number of changes and costs of change depend on maintainability.

 **中文翻译 (Chinese Translation):**
 预测假设：
 *   变更接受度取决于受变更影响组件的可维护性。
 *   实施变更会降低系统并降低其可维护性。
 *   维护成本取决于变更的数量，而变更成本取决于可维护性。

#### 7. What are some guidelines for maintenance prediction? (维护预测的一些指导方针是什么?)

 **From your notes (Lecture 10, Slide 15):**
 *   **Predicting maintainability:** What part of the system will be the most expensive to maintain?
 *   **Predicting maintenance cost:** What will be the lifetime maintenance cost of this system? What will be the costs of maintaining this system over the next year?
 *   **Predicting system changes:** What part of the system is most likely to be affected by change requests? How many change requests can be expected?

 **中文翻译 (Chinese Translation):**
 *   **预测可维护性:** 系统的哪个部分维护成本最高？
 *   **预测维护成本:** 该系统的生命周期维护成本是多少？未来一年维护该系统的成本是多少？
 *   **预测系统变更:** 系统的哪个部分最有可能受到变更请求的影响？预计会有多少变更请求？

#### 8. How to predict the number of required changes? (如何预测所需变更的数量?)

 **From your notes (Lecture 10, Slide 16):**
 *   Understand the system and its environment.
 *   Understand the relationships between a system and its environment.
 *   Factors influencing this relationship are:
     *   Number and complexity of system interfaces.
     *   Number of inherently volatile system requirements.
     *   The business processes where the system is used.
 *   Tightly coupled systems require changes whenever the environment is changed.

 **中文翻译 (Chinese Translation):**
 *   理解系统及其环境。
 *   理解系统与其环境之间的关系。
 *   影响这种关系的因素有：
     *   系统接口的数量和复杂性。
     *   固有易变系统需求的数量。
     *   系统所使用的业务流程。
 *   紧密耦合的系统在环境发生变化时需要进行变更。

#### 9. What are complexity metrics in maintenance prediction? (维护预测中的复杂性度量是什么?)

 **From your notes (Lecture 10, Slide 17):**
 *   Predictions of maintainability can be made by assessing the complexity of system components.
 *   Studies have shown that most maintenance effort is spent on a relatively small number of system components.
 *   Complexity depends on:
     *   Complexity of control structures.
     *   Complexity of data structures.
     *   Object, method (procedure) and module size.

 **中文翻译 (Chinese Translation):**
 *   通过评估系统组件的复杂性，可以预测可维护性。
 *   研究表明，大部分维护工作都花费在相对较少的系统组件上。
 *   复杂性取决于：
     *   控制结构的复杂性。
     *   数据结构的复杂性。
     *   对象、方法（过程）和模块的大小。

#### 10. What are process metrics in maintenance prediction? (维护预测中的过程度量是什么?)

 **From your notes (Lecture 10, Slide 18):**
 Process measurements may be used to assess maintainability:
 *   Number of requests for corrective maintenance.
 *   Average time required for impact analysis.
 *   Average time taken to implement a change request.
 *   Number of outstanding change requests.
 If any or all of these are increasing, this may indicate a decline in maintainability.

 **中文翻译 (Chinese Translation):**
 过程度量可用于评估可维护性：
 *   纠正性维护请求的数量。
 *   影响分析所需的平均时间。
 *   实施变更请求所需的平均时间。
 *   未完成变更请求的数量。
 如果其中任何一项或所有项都在增加，这可能表明可维护性正在下降。

#### 11. Describe evolution processes. (描述演进过程)

 **From your notes (Lecture 10, Slide 19):**
 Evolution processes depend on:
 *   The type of software being maintained.
 *   The development processes used.
 *   The skills and experience of the people involved.
 Proposals for change are the driver for system evolution.
 Change identification and evolution are cyclic and continue throughout the system lifetime.

 **中文翻译 (Chinese Translation):**
 演进过程取决于：
 *   所维护软件的类型。
 *   所使用的开发过程。
 *   相关人员的技能和经验。
 变更提议是系统演进的驱动力。
 变更识别和演进是循环的，并在系统整个生命周期中持续进行。

#### 12. Describe the system evolution process. (描述系统演进过程)

 **From your notes (Lecture 10, Slide 21):**
 The system evolution process involves:
 1.  **Change requests:** How much the system is affected by the changes & cost to implement the changes.
 2.  **Impact analysis:** All proposed changes (fault repair, adaptation and new functionality) are considered.
 3.  **Release planning:** Decide which changes to implement.
 4.  **Change implementation:** New version released. Changes proposed for the next release.

 **中文翻译 (Chinese Translation):**
 系统演进过程包括：
 1.  **变更请求:** 变更对系统的影响程度以及实施变更的成本。
 2.  **影响分析:** 考虑所有提议的变更（故障修复、适应性变更和新功能）。
 3.  **发布计划:** 决定要实施哪些变更。
 4.  **变更实施:** 发布新版本。为下一次发布提出变更建议。

#### 13. When are urgent change requests implemented? (何时实施紧急变更请求?)

 **From your notes (Lecture 10, Slide 23):**
 Urgent change requests may have to be implemented without going through all stages of the software engineering process as system problems need to be tackled urgently.
 This happens if:
 *   A serious system fault has to be repaired.
 *   Changes to the system's environment (e.g. an OS upgrade) have unexpected effects.
 *   There are business changes that require a very rapid response (e.g. the release of a competing product).

 **中文翻译 (Chinese Translation):**
 紧急变更请求可能需要在不经过软件工程过程所有阶段的情况下实施，因为系统问题需要紧急处理。
 这发生在以下情况：
 *   必须修复严重的系统故障。
 *   系统环境的变化（例如操作系统升级）产生了意外影响。
 *   业务变化需要非常快速的响应（例如竞争产品的发布）。

#### 14. What is system re-engineering? (什么是系统再工程?)

 **From your notes (Lecture 10, Slide 25):**
 System re-engineering is:
 *   Re-structuring or re-writing part or all of a **legacy system** without changing its functionality.
 *   Applicable where some but not all sub-systems of a larger system require frequent maintenance.
 *   Involves adding effort to make them easier to maintain.
 *   The system may be re-structured and re-documented.

 **中文翻译 (Chinese Translation):**
 系统再工程是：
 *   在不改变其功能的情况下，重构或重写 **遗留系统** 的部分或全部。
 *   适用于大型系统中部分而非全部子系统需要频繁维护的情况。
 *   涉及增加工作量以使其更易于维护。
 *   系统可以被重构和重新文档化。

#### 15. What are the advantages of re-engineering? (再工程的优点是什么?)

 **From your notes (Lecture 10, Slide 26):**
 *   **Reduced risk:** There is a high risk in new software development (development problems, staffing problems and specification problems).
 *   **Reduced cost:** The cost of re-engineering is often significantly less than the costs of developing new software.

 **中文翻译 (Chinese Translation):**
 *   **降低风险:** 新软件开发存在高风险（开发问题、人员配备问题和规范问题）。
 *   **降低成本:** 再工程的成本通常远低于开发新软件的成本。

#### 16. Describe the re-engineering process activities. (描述再工程过程活动)

 **From your notes (Lecture 10, Slide 29):**
 The re-engineering process activities include:
 *   **Source code translation:** Convert code to a new language using a translation tool.
 *   **Reverse engineering:** Analyze the program to understand it; information is extracted. Document its organization and function automatically.
 *   **Program structure improvement:** Restructure for understandability (partially automated).
 *   **Program modularization:** Reorganize the program structure; redundancy is removed (manual process).
 *   **Data re-engineering:** Clean-up and restructure system data to reflect program changes (e.g. finding and correcting mistakes, removing duplicate records, etc.).

 **中文翻译 (Chinese Translation):**
 再工程过程活动包括：
 *   **源代码翻译:** 使用翻译工具将代码转换为新语言。
 *   **逆向工程:** 分析程序以理解它；提取信息。自动记录其组织和功能。
 *   **程序结构改进:** 重构以提高可理解性（部分自动化）。
 *   **程序模块化:** 重组程序结构；消除冗余（手动过程）。
 *   **数据再工程:** 清理和重构系统数据以反映程序变更（例如，查找和纠正错误，删除重复记录等）。

#### 17. What are the re-engineering cost factors? (再工程的成本因素是什么?)

 **From your notes (Lecture 10, Slide 31):**
 The cost of re-engineering depends on:
 *   The quality of the software to be reengineered.
 *   The tool support available for reengineering.
 *   The extent of the data conversion which is required.
 *   The availability of expert staff for reengineering. (This can be a problem with old systems based on technology that is no longer widely used).

 **中文翻译 (Chinese Translation):**
 再工程的成本取决于：
 *   待再工程软件的质量。
 *   可用于再工程的工具支持。
 *   所需数据转换的程度。
 *   可用于再工程的专家人员的可用性。（这对于基于不再广泛使用的技术的旧系统可能是一个问题）。

#### 18. Describe legacy system evolution. (描述遗留系统演进)

 **From your notes (Lecture 10, Slide 32):**
 *   Separation between software development and software maintenance is unhelpful.
 *   Organisations that rely on legacy systems must choose a strategy for evolving these systems:
     *   Scrap the system completely and modify business processes so that it is no longer required.
     *   Continue maintaining the system.
     *   Transform the system by re-engineering to improve its maintainability.
     *   Replace the system with a new system.
 *   The strategy chosen should depend on the system quality and its business value.

 **中文翻译 (Chinese Translation):**
 *   软件开发和软件维护之间的分离是无益的。
 *   依赖遗留系统的组织必须选择一个演进这些系统的策略：
     *   完全废弃系统并修改业务流程，使其不再需要。
     *   继续维护系统。
     *   通过再工程改造系统以提高其可维护性。
     *   用新系统替换现有系统。
 *   所选择的策略应取决于系统质量和其业务价值。

#### 19. Describe legacy system categories based on business value and quality. (根据业务价值和质量描述遗留系统类别)

 **From your notes (Lecture 10, Slide 34):**
 *   **Low quality, low business value:** (operation expensive, return small) - These systems should be scrapped.
 *   **Low-quality, high-business value:** These make an important business contribution but are expensive to maintain. Should be re-engineered or replaced if a suitable system is available.
 *   **High-quality, low-business value:** Don't contribute much to the business, expensive to maintain. Replace with commercial-off-the-shelf (COTS), scrap completely or maintain.
 *   **High-quality, high business value:** Continue in operation using normal system maintenance.

 **中文翻译 (Chinese Translation):**
 *   **低质量、低业务价值:** (运营成本高，回报小) - 这些系统应该被废弃。
 *   **低质量、高业务价值:** 这些系统对业务有重要贡献，但维护成本高。如果存在合适的系统，应该进行再工程或替换。
 *   **高质量、低业务价值:** 对业务贡献不大，维护成本高。可以用现成的商业软件 (COTS) 替换，完全废弃或继续维护。
 *   **高质量、高业务价值:** 继续使用正常系统维护。

#### 20. How to assess business value and system quality? (如何评估业务价值和系统质量?)

 **From your notes (Lecture 10, Slide 35, 36, 37):**
 **Business value assessment:**
 *   Assessment should take different viewpoints into account:
     *   System end-users;
     *   Business customers;
     *   Line managers;
     *   IT managers;
     *   Senior managers.
 *   Interview different stakeholders and collate results.

 **System quality assessment:**
 *   **Business process assessment:** How well does the business process support the current goals of the business?
 *   **Environment assessment:** How effective is the system's environment and how expensive is it to maintain?
 *   **Application assessment:** What is the quality of the application software system?

 **System measurement (quantitative data for quality assessment):**
 *   The number of system change requests;
 *   The number of different user interfaces used by the system;
 *   The volume of data used by the system.

 **中文翻译 (Chinese Translation):**
 **业务价值评估：**
 *   评估应考虑不同的观点：
     *   系统最终用户；
     *   业务客户；
     *   直线经理；
     *   IT经理；
     *   高级经理。
 *   访谈不同的利益相关者并整理结果。

 **系统质量评估：**
 *   **业务流程评估:** 业务流程如何支持当前的业务目标？
 *   **环境评估:** 系统环境的有效性如何，维护成本高吗？
 *   **应用评估:** 应用软件系统的质量如何？

 **系统度量（用于质量评估的定量数据）：**
 *   系统变更请求的数量；
 *   系统使用的不同用户界面的数量；
 *   系统使用的数据量。

---

#### 3. What are the costs of maintenance? (维护成本有哪些?)

 **From your notes (Lecture 10, Slide 11):**
 *   Usually greater than development costs (2* to 100* depending on the application).
 *   Affected by both technical and non-technical factors.
 *   Increases as software is maintained.
 *   Maintenance corrupts the software structure so makes further maintenance more difficult.
 *   Ageing software can have high support costs (e.g. old languages, compilers etc.).

 **中文翻译 (Chinese Translation):**
 *   通常高于开发成本（根据应用不同，可能是2到100倍）。
 *   受技术和非技术因素影响。
 *   随着软件的维护而增加。
 *   维护会破坏软件结构，使后续维护更加困难。
 *   老化的软件可能产生高昂的支持成本（例如，旧的语言、编译器等）。

#### 4. What are the factors influencing maintenance costs? (影响维护成本的因素有哪些?)

 **From your notes (Lecture 10, Slide 13):**
 *   **Team stability:** Maintenance costs are reduced if the same staff are involved with them for some time.
 *   **Contractual responsibility:** The developers of a system may have no contractual responsibility for maintenance so there is no incentive to design for future change.
 *   **Staff skills:** Maintenance staff are often inexperienced and have limited domain knowledge.
 *   **Program age and structure:** As programs age, their structure is degraded and they become harder to understand and change.

 **中文翻译 (Chinese Translation):**
 *   **团队稳定性:** 如果由同一批人员长期参与维护，维护成本会降低。
 *   **合同责任:** 系统开发者可能没有维护的合同责任，因此没有动力为未来的变更进行设计。
 *   **员工技能:** 维护人员通常经验不足，领域知识有限。
 *   **程序年龄和结构:** 随着程序的老化，其结构会退化，变得更难理解和修改。

#### 5. What is maintenance prediction? (什么是维护预测?)

 **From your notes (Lecture 10, Slide 14):**
 Maintenance prediction is concerned with:
 *   Assessing parts of the system that may cause problems.
 *   Assessing parts of the system that may have high maintenance costs.

 **中文翻译 (Chinese Translation):**
 维护预测关注的是：
 *   评估系统中可能导致问题的部分。
 *   评估系统中可能产生高维护成本的部分。

#### 6. What are the assumptions for maintenance prediction? (维护预测的假设是什么?)

 **From your notes (Lecture 10, Slide 14):**
 Prediction Assumptions:
 *   Change acceptance depends on the maintainability of the components affected by the change.
 *   Implementing changes degrades the system and reduces its maintainability.
 *   Maintenance costs depend on the number of changes and costs of change depend on maintainability.

 **中文翻译 (Chinese Translation):**
 预测假设：
 *   变更接受度取决于受变更影响组件的可维护性。
 *   实施变更会降低系统并降低其可维护性。
 *   维护成本取决于变更的数量，而变更成本取决于可维护性。

#### 7. What are some guidelines for maintenance prediction? (维护预测的一些指导方针是什么?)

 **From your notes (Lecture 10, Slide 15):**
 *   **Predicting maintainability:** What part of the system will be the most expensive to maintain?
 *   **Predicting maintenance cost:** What will be the lifetime maintenance cost of this system? What will be the costs of maintaining this system over the next year?
 *   **Predicting system changes:** What part of the system is most likely to be affected by change requests? How many change requests can be expected?

 **中文翻译 (Chinese Translation):**
 *   **预测可维护性:** 系统的哪个部分维护成本最高？
 *   **预测维护成本:** 该系统的生命周期维护成本是多少？未来一年维护该系统的成本是多少？
 *   **预测系统变更:** 系统的哪个部分最有可能受到变更请求的影响？预计会有多少变更请求？

#### 8. How to predict the number of required changes? (如何预测所需变更的数量?)

 **From your notes (Lecture 10, Slide 16):**
 *   Understand the system and its environment.
 *   Understand the relationships between a system and its environment.
 *   Factors influencing this relationship are:
     *   Number and complexity of system interfaces.
     *   Number of inherently volatile system requirements.
     *   The business processes where the system is used.
 *   Tightly coupled systems require changes whenever the environment is changed.

 **中文翻译 (Chinese Translation):**
 *   理解系统及其环境。
 *   理解系统与其环境之间的关系。
 *   影响这种关系的因素有：
     *   系统接口的数量和复杂性。
     *   固有易变系统需求的数量。
     *   系统所使用的业务流程。
 *   紧密耦合的系统在环境发生变化时需要进行变更。

#### 9. What are complexity metrics in maintenance prediction? (维护预测中的复杂性度量是什么?)

 **From your notes (Lecture 10, Slide 17):**
 *   Predictions of maintainability can be made by assessing the complexity of system components.
 *   Studies have shown that most maintenance effort is spent on a relatively small number of system components.
 *   Complexity depends on:
     *   Complexity of control structures.
     *   Complexity of data structures.
     *   Object, method (procedure) and module size.

 **中文翻译 (Chinese Translation):**
 *   通过评估系统组件的复杂性，可以预测可维护性。
 *   研究表明，大部分维护工作都花费在相对较少的系统组件上。
 *   复杂性取决于：
     *   控制结构的复杂性。
     *   数据结构的复杂性。
     *   对象、方法（过程）和模块的大小。

#### 10. What are process metrics in maintenance prediction? (维护预测中的过程度量是什么?)

 **From your notes (Lecture 10, Slide 18):**
 Process measurements may be used to assess maintainability:
 *   Number of requests for corrective maintenance.
 *   Average time required for impact analysis.
 *   Average time taken to implement a change request.
 *   Number of outstanding change requests.
 If any or all of these are increasing, this may indicate a decline in maintainability.

 **中文翻译 (Chinese Translation):**
 过程度量可用于评估可维护性：
 *   纠正性维护请求的数量。
 *   影响分析所需的平均时间。
 *   实施变更请求所需的平均时间。
 *   未完成变更请求的数量。
 如果其中任何一项或所有项都在增加，这可能表明可维护性正在下降。

#### 11. Describe evolution processes. (描述演进过程)

 **From your notes (Lecture 10, Slide 19):**
 Evolution processes depend on:
 *   The type of software being maintained.
 *   The development processes used.
 *   The skills and experience of the people involved.
 Proposals for change are the driver for system evolution.
 Change identification and evolution are cyclic and continue throughout the system lifetime.

 **中文翻译 (Chinese Translation):**
 演进过程取决于：
 *   所维护软件的类型。
 *   所使用的开发过程。
 *   相关人员的技能和经验。
 变更提议是系统演进的驱动力。
 变更识别和演进是循环的，并在系统整个生命周期中持续进行。

#### 12. Describe the system evolution process. (描述系统演进过程)

 **From your notes (Lecture 10, Slide 21):**
 The system evolution process involves:
 1.  **Change requests:** How much the system is affected by the changes & cost to implement the changes.
 2.  **Impact analysis:** All proposed changes (fault repair, adaptation and new functionality) are considered.
 3.  **Release planning:** Decide which changes to implement.
 4.  **Change implementation:** New version released. Changes proposed for the next release.

 **中文翻译 (Chinese Translation):**
 系统演进过程包括：
 1.  **变更请求:** 变更对系统的影响程度以及实施变更的成本。
 2.  **影响分析:** 考虑所有提议的变更（故障修复、适应性变更和新功能）。
 3.  **发布计划:** 决定要实施哪些变更。
 4.  **变更实施:** 发布新版本。为下一次发布提出变更建议。

#### 13. When are urgent change requests implemented? (何时实施紧急变更请求?)

 **From your notes (Lecture 10, Slide 23):**
 Urgent change requests may have to be implemented without going through all stages of the software engineering process as system problems need to be tackled urgently.
 This happens if:
 *   A serious system fault has to be repaired.
 *   Changes to the system's environment (e.g. an OS upgrade) have unexpected effects.
 *   There are business changes that require a very rapid response (e.g. the release of a competing product).

 **中文翻译 (Chinese Translation):**
 紧急变更请求可能需要在不经过软件工程过程所有阶段的情况下实施，因为系统问题需要紧急处理。
 这发生在以下情况：
 *   必须修复严重的系统故障。
 *   系统环境的变化（例如操作系统升级）产生了意外影响。
 *   业务变化需要非常快速的响应（例如竞争产品的发布）。

#### 14. What is system re-engineering? (什么是系统再工程?)

 **From your notes (Lecture 10, Slide 25):**
 System re-engineering is:
 *   Re-structuring or re-writing part or all of a **legacy system** without changing its functionality.
 *   Applicable where some but not all sub-systems of a larger system require frequent maintenance.
 *   Involves adding effort to make them easier to maintain.
 *   The system may be re-structured and re-documented.

 **中文翻译 (Chinese Translation):**
 系统再工程是：
 *   在不改变其功能的情况下，重构或重写 **遗留系统** 的部分或全部。
 *   适用于大型系统中部分而非全部子系统需要频繁维护的情况。
 *   涉及增加工作量以使其更易于维护。
 *   系统可以被重构和重新文档化。

#### 15. What are the advantages of re-engineering? (再工程的优点是什么?)

 **From your notes (Lecture 10, Slide 26):**
 *   **Reduced risk:** There is a high risk in new software development (development problems, staffing problems and specification problems).
 *   **Reduced cost:** The cost of re-engineering is often significantly less than the costs of developing new software.

 **中文翻译 (Chinese Translation):**
 *   **降低风险:** 新软件开发存在高风险（开发问题、人员配备问题和规范问题）。
 *   **降低成本:** 再工程的成本通常远低于开发新软件的成本。

#### 16. Describe the re-engineering process activities. (描述再工程过程活动)

 **From your notes (Lecture 10, Slide 29):**
 The re-engineering process activities include:
 *   **Source code translation:** Convert code to a new language using a translation tool.
 *   **Reverse engineering:** Analyze the program to understand it; information is extracted. Document its organization and function automatically.
 *   **Program structure improvement:** Restructure for understandability (partially automated).
 *   **Program modularization:** Reorganize the program structure; redundancy is removed (manual process).
 *   **Data re-engineering:** Clean-up and restructure system data to reflect program changes (e.g. finding and correcting mistakes, removing duplicate records, etc.).

 **中文翻译 (Chinese Translation):**
 再工程过程活动包括：
 *   **源代码翻译:** 使用翻译工具将代码转换为新语言。
 *   **逆向工程:** 分析程序以理解它；提取信息。自动记录其组织和功能。
 *   **程序结构改进:** 重构以提高可理解性（部分自动化）。
 *   **程序模块化:** 重组程序结构；消除冗余（手动过程）。
 *   **数据再工程:** 清理和重构系统数据以反映程序变更（例如，查找和纠正错误，删除重复记录等）。

#### 17. What are the re-engineering cost factors? (再工程的成本因素是什么?)

 **From your notes (Lecture 10, Slide 31):**
 The cost of re-engineering depends on:
 *   The quality of the software to be reengineered.
 *   The tool support available for reengineering.
 *   The extent of the data conversion which is required.
 *   The availability of expert staff for reengineering. (This can be a problem with old systems based on technology that is no longer widely used).

 **中文翻译 (Chinese Translation):**
 再工程的成本取决于：
 *   待再工程软件的质量。
 *   可用于再工程的工具支持。
 *   所需数据转换的程度。
 *   可用于再工程的专家人员的可用性。（这对于基于不再广泛使用的技术的旧系统可能是一个问题）。

#### 18. Describe legacy system evolution. (描述遗留系统演进)

 **From your notes (Lecture 10, Slide 32):**
 *   Separation between software development and software maintenance is unhelpful.
 *   Organisations that rely on legacy systems must choose a strategy for evolving these systems:
     *   Scrap the system completely and modify business processes so that it is no longer required.
     *   Continue maintaining the system.
     *   Transform the system by re-engineering to improve its maintainability.
     *   Replace the system with a new system.
 *   The strategy chosen should depend on the system quality and its business value.

 **中文翻译 (Chinese Translation):**
 *   软件开发和软件维护之间的分离是无益的。
 *   依赖遗留系统的组织必须选择一个演进这些系统的策略：
     *   完全废弃系统并修改业务流程，使其不再需要。
     *   继续维护系统。
     *   通过再工程改造系统以提高其可维护性。
     *   用新系统替换现有系统。
 *   所选择的策略应取决于系统质量和其业务价值。

#### 19. Describe legacy system categories based on business value and quality. (根据业务价值和质量描述遗留系统类别)

 **From your notes (Lecture 10, Slide 34):**
 *   **Low quality, low business value:** (operation expensive, return small) - These systems should be scrapped.
 *   **Low-quality, high-business value:** These make an important business contribution but are expensive to maintain. Should be re-engineered or replaced if a suitable system is available.
 *   **High-quality, low-business value:** Don't contribute much to the business, expensive to maintain. Replace with commercial-off-the-shelf (COTS), scrap completely or maintain.
 *   **High-quality, high business value:** Continue in operation using normal system maintenance.

 **中文翻译 (Chinese Translation):**
 *   **低质量、低业务价值:** (运营成本高，回报小) - 这些系统应该被废弃。
 *   **低质量、高业务价值:** 这些系统对业务有重要贡献，但维护成本高。如果存在合适的系统，应该进行再工程或替换。
 *   **高质量、低业务价值:** 对业务贡献不大，维护成本高。可以用现成的商业软件 (COTS) 替换，完全废弃或继续维护。
 *   **高质量、高业务价值:** 继续使用正常系统维护。

#### 20. How to assess business value and system quality? (如何评估业务价值和系统质量?)

 **From your notes (Lecture 10, Slide 35, 36, 37):**
 **Business value assessment:**
 *   Assessment should take different viewpoints into account:
     *   System end-users;
     *   Business customers;
     *   Line managers;
     *   IT managers;
     *   Senior managers.
 *   Interview different stakeholders and collate results.

 **System quality assessment:**
 *   **Business process assessment:** How well does the business process support the current goals of the business?
 *   **Environment assessment:** How effective is the system's environment and how expensive is it to maintain?
 *   **Application assessment:** What is the quality of the application software system?

 **System measurement (quantitative data for quality assessment):**
 *   The number of system change requests;
 *   The number of different user interfaces used by the system;
 *   The volume of data used by the system.

 **中文翻译 (Chinese Translation):**
 **业务价值评估：**
 *   评估应考虑不同的观点：
     *   系统最终用户；
     *   业务客户；
     *   直线经理；
     *   IT经理；
     *   高级经理。
 *   访谈不同的利益相关者并整理结果。

 **系统质量评估：**
 *   **业务流程评估:** 业务流程如何支持当前的业务目标？
 *   **环境评估:** 系统环境的有效性如何，维护成本高吗？
 *   **应用评估:** 应用软件系统的质量如何？

 **系统度量（用于质量评估的定量数据）：**
 *   系统变更请求的数量；
 *   系统使用的不同用户界面的数量；
 *   系统使用的数据量。

---
