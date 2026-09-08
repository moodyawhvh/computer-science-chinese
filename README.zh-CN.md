<div align="center">

# computer-science 中文文档

[![原项目](https://img.shields.io/badge/原项目-ossu--computer-science-blue?style=flat-square&logo=github)](https://github.com/ossu/computer-science)
[![GitHub Stars](https://img.shields.io/github/stars/ossu/computer-science?style=flat-square&label=原项目Stars)](https://github.com/ossu/computer-science/stargazers)
[![微信联系](https://img.shields.io/badge/微信-uaycar-brightgreen?style=flat-square&logo=wechat)](#)

</div>

---

> 本文档是 [ossu/computer-science](https://github.com/ossu/computer-science)(Path to a free self-taught education in Computer Science)的中文汉化版,涵盖项目定位、课程遴选标准、学习方式与课程体系导读。英文课程名与链接保留原样,便于直接跳转。完整内容请以原仓库与 [OSSU CS 官网](https://cs.ossu.dev) 为准。

**代部署 / 定制服务 / 技术咨询 请添加微信:uaycar**

---

## 目录

- [项目简介](#项目简介)
- [社区](#社区)
- [课程体系总览](#课程体系总览)
  - [先修要求](#先修要求)
  - [入门 CS(Intro CS)](#入门-csintro-cs)
  - [核心 CS(Core CS)](#核心-cscore-cs)
  - [进阶 CS(Advanced CS)](#进阶-csadvanced-cs)
  - [毕业项目(Final Project)](#毕业项目final-project)
- [完成之后](#完成之后)
- [行为准则与进度追踪](#行为准则与进度追踪)

## 项目简介

OSSU 课程体系是一套**利用在线资源完成的计算机科学完整教育**。它不仅用于职业培训或技能提升,更面向那些希望在计算学科核心概念上获得扎实、全面基础的人——前提是你有足够的自律、意愿和(最重要的)良好的学习习惯,主要靠自学完成,同时有全球学习者的社区支持。

课程设计对标计算机科学本科专业的学位要求(不含通识课),默认大多数学习者已在 CS 之外受过教育。所选课程均为世界顶级水平,多来自哈佛、普林斯顿、MIT 等,并满足以下硬性标准:

**入选课程必须**:
- 开放注册;
- 定期开课(最好支持自学节奏,否则每年多次开课);
- 教学材料与教学法质量高;
- 符合 [CS 2013](https://github.com/ossu/computer-science/blob/master/CURRICULAR_GUIDELINES.md) 本科计算机科学教学大纲。

当没有课程满足标准时,会以书籍补充;不进入主线但质量很高的课程/书籍,收录在 extras 扩展课程与延伸阅读中。

**学制**:规划得当、每周约 20 小时,约两年可完成。官方提供[学习时长估算电子表格](https://docs.google.com/spreadsheets/d/1y2kMsIg9VaHMVmw35x_aH1hpty3V-ZMuV2jA13P_Cgo/copy):复制后在 `Timeline` 页填入开始日期与每周投入,学习中在 `Curriculum Data` 页录入实际完成日期,即可动态更新预计完成时间。注意表格可能滞后于课程更新,以 [OSSU CS 网站](https://cs.ossu.dev) 和原仓库为准。

**费用**:几乎所有课程材料免费;少数课程的作业/考试/项目评分可能收费。[Coursera](https://www.coursera.support/s/article/209819033-Apply-for-Financial-Aid-or-a-Scholarship?language=en_US) 与 [edX](https://courses.edx.org/financial-assistance/) 均提供助学金。按自己的时间与预算决定投入,但记住:成功是买不来的!

**学习方式**:可独立也可结伴、可顺序也可跳读。建议:
- Core CS 全部修读,仅在确定已掌握时跳过某门课;
- 简单起见按自上而下顺序学习;也有不少人把数学课与入门课并行修读;
- Advanced CS 为选修:选定一个方向(如高级编程),修完该方向下所有课程;也可自定方向并在 Discord 社区征求意见。

**内容政策**:公开晒作业时只分享你有权分享的文件,尊重每门课开头签署的行为准则。

- [参与贡献](https://github.com/ossu/computer-science/blob/master/CONTRIBUTING.md)
- [获取帮助(FAQ 与聊天室)](https://github.com/ossu/computer-science/blob/master/HELP.md)

## 社区

- 官方 [Discord 服务器](https://discord.gg/wuytwK5s9h):与其他 OSSU 学员交流的第一站,欢迎先去自我介绍;
- 通过 [GitHub Issues](https://github.com/ossu/computer-science/issues) 反馈课程问题或提出课程调整建议;
- 在 [LinkedIn](https://www.linkedin.com/school/11272443/) 资料中添加 Open Source Society University 学校信息。

> **注意**:搜索 OSSU 时可能遇到第三方/已弃用/过时的资源(弃用的 firebase 应用、trello 看板、第三方 notion 模板等),请一律忽略,只使用 [OSSU CS 网站](https://cs.ossu.dev) 或原仓库。

## 课程体系总览

### 先修要求

- [Core CS](#核心-cscore-cs) 假设你已完成[高中数学](https://ossu.dev/precollege-math)(代数、几何、微积分预备);
- [Advanced CS](#进阶-csadvanced-cs) 假设你已修完 Core CS 全部课程;
- 进阶系统方向还要求修过基础物理课(如高中 AP 物理)。

### 入门 CS(Intro CS)

带你初步认识计算机科学与编程的世界,体验后续内容的风味。如果学完还意犹未尽,那 CS 很可能适合你!覆盖主题:计算、命令式编程、基础数据结构与算法等。

| 课程 | 时长 | 投入 | 先修 | 讨论 |
|:--|:--:|:--:|:--:|:--:|
| [Introduction to Computer Science and Programming using Python](https://github.com/ossu/computer-science/blob/master/coursepages/intro-cs/README.md) | 14 周 | 每周 6-10 小时 | [高中代数](https://ossu.dev/precollege-math) | [Discord](https://discord.gg/jvchSm9) |

### 核心 CS(Core CS)

Core CS 下所有课程**均为必修**(另有标注除外),大致对应本科前三年的公共必修课。

#### 核心编程(Core programming)

覆盖函数式编程、面向测试的设计、需求分析、常见设计模式、单元测试、面向对象设计、静态/动态类型、ML 族与 Lisp 族语言、Ruby 等。代表课程:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) | 13 周 | 每周 8-10 小时 | 无 |
| [Programming Languages](https://courses.cs.washington.edu/courses/cse341/19sp/#lectures) | 11 周 | 每周 4-8 小时 | Systematic Program Design |
| [Object-Oriented Design](https://course.ccs.neu.edu/cs3500f19/) | 13 周 | 每周 5-10 小时 | Class-based Program Design |
| [Software Architecture](https://www.coursera.org/learn/software-architecture) | 4 周 | 每周 2-5 小时 | Object Oriented Design |

#### 核心数学(Core math)

离散数学是算法与数据结构的先修且密切相关;微积分既为离散数学铺路,也培养数学成熟度。覆盖离散数学、数学证明、基础统计、O 记号、离散概率等。代表课程:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Calculus 1A: Differentiation](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.1x+2T2019/about)([替代](https://ocw.mit.edu/courses/mathematics/18-01sc-single-variable-calculus-fall-2010/index.htm)) | 13 周 | 每周 6-10 小时 | [高中数学](https://ossu.dev/precollege-math) |
| [Calculus 1B: Integration](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.2x+3T2019/about) | 13 周 | 每周 5-10 小时 | Calculus 1A |
| [Calculus 1C: Coordinate Systems & Infinite Series](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.3x+1T2020/about) | 6 周 | 每周 5-10 小时 | Calculus 1B |
| [Mathematics for Computer Science](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about)([替代](https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/)) | 13 周 | 每周 5 小时 | Calculus 1C |

#### CS 工具(CS Tools)

懂理论还不够,你还要写程序。学会业界广泛使用的效率工具,让后续学习事半功倍。覆盖终端与 Shell 脚本、vim、命令行环境、版本控制等。

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 周 | 每周 12 小时 | 无 |

#### 核心系统(Core systems)

覆盖过程式编程、手动内存管理、布尔代数、门电路、计算机体系结构、汇编与机器语言、虚拟机、编译器、操作系统、网络协议等。代表课程:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Build a Modern Computer from First Principles: From Nand to Tetris](https://www.coursera.org/learn/build-a-computer)([替代](https://www.nand2tetris.org/)) | 6 周 | 每周 7-13 小时 | 任一 C 风格语言 |
| [Build a Modern Computer from First Principles: Nand to Tetris Part II](https://www.coursera.org/learn/nand2tetris2) | 6 周 | 每周 12-18 小时 | Nand to Tetris Part I |
| [Operating Systems: Three Easy Pieces](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md) | 10-12 周 | 每周 6-10 小时 | Nand to Tetris Part II |
| [Computer Networking: a Top-Down Approach](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 周 | 每周 4-12 小时 | 代数、概率、基础 CS |

#### 核心理论(Core theory)

覆盖分治、排序与查找、随机化算法、图搜索、最短路径、数据结构、贪心算法、最小生成树、动态规划、NP 完全性等。代表课程:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Algorithms: Design and Analysis, Part 1](https://www.edx.org/learn/algorithms/stanford-university-algorithms-design-and-analysis-part-1)([替代](https://www.algorithmsilluminated.org/)) | 8 周 | 每周 4-8 小时 | 任一编程语言、Mathematics for CS |
| [Algorithms: Design and Analysis, Part 2](https://www.edx.org/learn/algorithms/stanford-university-algorithms-design-and-analysis-part-2) | 8 周 | 每周 4-8 小时 | Algorithms Part 1 |

#### 核心安全(Core security)

覆盖机密性/完整性/可用性、安全设计、防御性编程、威胁与攻击、网络安全、密码学等。必修 [Cybersecurity Fundamentals](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals)(8 周)、[Principles of Secure Coding](https://www.coursera.org/learn/secure-coding-principles)(4 周)、[Identifying Security Vulnerabilities](https://www.coursera.org/learn/identifying-security-vulnerabilities)(4 周),再从 C/C++ 漏洞利用或 Java 漏洞利用与防护两门课中**任选一门**。

#### 核心应用(Core applications)

覆盖敏捷方法、REST、软件规格、重构、关系数据库、事务处理、数据建模、神经网络、监督/无监督学习、OpenGL、光线追踪等。代表课程:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Databases: Modeling and Theory](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 周 | 每周 10 小时 | 核心编程 |
| [Databases: Relational Databases and SQL](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 周 | 每周 10 小时 | 核心编程 |
| [Machine Learning](https://www.deeplearning.ai/courses/machine-learning-specialization/) | 11 周 | 每周 9 小时 | 基础编程 |
| [Computer Graphics](https://www.edx.org/learn/computer-graphics/the-university-of-california-san-diego-computer-graphics)([替代](https://cseweb.ucsd.edu/~viscomp/classes/cse167/wi22/schedule.html)) | 6 周 | 每周 12 小时 | C++/Java、基础线性代数 |
| [Software Engineering: Introduction](https://www.edx.org/learn/software-engineering/university-of-british-columbia-software-engineering-introduction) | 6 周 | 每周 8-10 小时 | 核心编程 + 有一定规模的项目经验 |

#### 核心伦理(Core ethics)

覆盖社会背景、分析工具、职业伦理、知识产权、隐私与公民自由等。必修 [Ethics, Technology and Engineering](https://www.coursera.org/learn/ethics-technology-engineering)(9 周)、[Introduction to Intellectual Property](https://www.coursera.org/learn/introduction-intellectual-property)(4 周)、[Data Privacy Fundamentals](https://www.coursera.org/learn/northeastern-data-privacy)(3 周)。

### 进阶 CS(Advanced CS)

修完 Core CS 全部必修课后,按兴趣从进阶课程中选课。不必修完某子类下的每一门,但应修完与你目标领域相关的每一门。

#### 进阶编程(Advanced programming)

覆盖调试的理论与实践、目标导向编程、并行计算、面向对象分析与设计、UML、大规模软件架构与设计等。代表课程:[Parallel Programming](https://www.coursera.org/learn/scala-parallel-programming)(4 周)、[Compilers](https://www.edx.org/learn/computer-science/stanford-university-compilers)(9 周)、[Introduction to Haskell](https://www.seas.upenn.edu/~cis194/fall16/)(14 周)、[Learn Prolog Now!](https://www.let.rug.nl/bos/lpn//lpnpage.php?pageid=online)(12 周)、[Software Debugging](https://www.youtube.com/playlist?list=PLAwxTw4SYaPkxK63TiT88oEe-AIBhr96A)(8 周)、[Software Testing](https://www.youtube.com/playlist?list=PLAwxTw4SYaPkWVHeC_8aSIbSxE_NXI76g)(4 周)。

#### 进阶系统(Advanced systems)

覆盖数字信号、组合逻辑、CMOS 技术、时序逻辑、有限状态机、处理器指令集、缓存、流水线、虚拟化、并行处理、虚拟内存、同步原语、系统调用接口等。三门 [Computation Structures](https://learning.edx.org/course/course-v1:MITx+6.004.1x_3+3T2016) 系列课(数字电路/计算机体系结构/计算机组成),各 10 周、每周 6 小时,依次递进。

#### 进阶理论(Advanced theory)

覆盖形式语言、图灵机、可计算性、事件驱动并发、自动机、分布式共享内存、共识算法、状态机复制、计算几何、命题逻辑等。代表课程:[Theory of Computation](https://ocw.mit.edu/courses/18-404j-theory-of-computation-fall-2020/)(13 周)、[Computational Geometry](https://www.edx.org/learn/geometry/tsinghua-university-ji-suan-ji-he-computational-geometry)(16 周,清华)、[Algorithmic Game Theory](https://timroughgarden.org/f13/f13.html)(10 周)。

#### 进阶信息安全(Advanced Information Security)

代表课程:[Web Security Fundamentals](https://www.edx.org/learn/computer-security/ku-leuven-web-security-fundamentals)(5 周)、[Security Governance & Compliance](https://www.coursera.org/learn/security-governance-compliance)(3 周)、[Digital Forensics Concepts](https://www.coursera.org/learn/digital-forensics-concepts)(3 周),以及 Linux 基金会的安全软件开发三部曲(需求设计与复用 / 实现 / 验证与专题),各 7 周、每周 1-2 小时。

#### 进阶数学(Advanced math)

代表课程:[Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)(视频系列)、[Linear Algebra](https://ocw.mit.edu/courses/mathematics/18-06sc-linear-algebra-fall-2011/)(14 周)、[Introduction to Numerical Methods](https://ocw.mit.edu/courses/mathematics/18-335j-introduction-to-numerical-methods-spring-2019/index.htm)(14 周)、[Introduction to Formal Logic](https://forallx.openlogicproject.org/)(10 周)、[Probability](https://stat110.hsites.harvard.edu/)(15 周,哈佛 Stat110)。

### 毕业项目(Final Project)

学习的目的在于实践。各课程的作业与考试都是为了让你用所学解决真实问题。完成 Core CS 与相关进阶课程后,找一个能用所学知识解决的问题:可以做出全新作品,也可以改进你日常使用但不够顺手的工具/程序。想要更多指导的学员可以选择一系列面向项目的课程,例如:

| 课程 | 时长 | 投入 | 先修 |
|:--|:--:|:--:|:--:|
| [Fullstack Open](https://fullstackopen.com/en/) | 12 周 | 每周 15 小时 | 编程基础 |
| [Modern Robotics](https://modernrobotics.northwestern.edu) | 26 周 | 每周 2-5 小时 | 大一物理、线性代数、微积分 |
| [Data Mining (Specialization)](https://www.coursera.org/specializations/data-mining) | 30 周 | 每周 2-5 小时 | 机器学习 |
| [Big Data (Specialization)](https://www.coursera.org/specializations/big-data) | 30 周 | 每周 3-5 小时 | 无 |
| [Cloud Computing (Specialization)](https://www.coursera.org/specializations/cloud-computing) | 30 周 | 每周 2-6 小时 | C++ |
| [Data Science (Specialization)](https://www.coursera.org/specializations/jhu-data-science) | 43 周 | 每周 1-6 小时 | 无 |
| [Game Design and Development with Unity 2020 (Specialization)](https://www.coursera.org/specializations/game-design-and-development) | 6 个月 | 每周 5 小时 | 编程、交互设计 |

## 完成之后

完成上述全部要求后,你已达到计算机科学本科同等学力。祝贺!接下来的可能性无穷无尽:

- 找一份开发者工作!
- 阅读 [延伸书单](https://github.com/ossu/computer-science/blob/master/extras/readings.md),磨砺技能、拓展视野;
- 参加本地开发者聚会(如 [meetup.com](https://www.meetup.com/));
- 关注软件开发领域的新兴技术:通过 [Elixir](https://elixir-lang.org/) 探索 **Actor 模型**,通过 [Rust](https://www.rust-lang.org/) 探索**借用与生命周期**(无 GC 的内存与线程安全),通过 [Idris](https://www.idris-lang.org/) 探索**依值类型系统**。

## 行为准则与进度追踪

- 行为准则见 [OSSU Code of Conduct](https://github.com/ossu/code-of-conduct);
- 进度追踪:把[原仓库](https://github.com/ossu/computer-science) Fork 到自己账号,完成一项就在旁边打 ✅,这既是你的[看板](https://en.wikipedia.org/wiki/Kanban_board),也是最省时的实现方式。

---

## 版权与致谢

> **代部署 / 定制服务 / 技术咨询 请添加微信:uaycar**

本项目为 [ossu/computer-science](https://github.com/ossu/computer-science) 的中文翻译介绍版本,仅汉化文档供中文读者参考,不包含、不复制任何源代码。原项目及所有课程内容版权归 OSSU 及各课程提供方(MIT、哈佛、斯坦福等)所有,遵循其原始许可证。

**如果对你有帮助,请给原项目 [ossu/computer-science](https://github.com/ossu/computer-science) 点个 Star!** ⭐
