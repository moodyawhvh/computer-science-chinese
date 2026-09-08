> 🌐 本文档由 [ossu/computer-science](https://github.com/ossu/computer-science) 翻译,英文原版见原项目。

# 变更日志

**注意**:课程体系正在为 v9 进行整体审校,主要是对照[课程设计准则](CURRICULAR_GUIDELINES.md)核查现有推荐课程,补充缺失主题,删减冗余或超纲课程。相关的意见征求(RFC)一旦通过,改动会立即应用到课程体系。整体审校完成后,版本号将升级到 v9。

本项目的所有重要变更都会记录在本文件中。
本项目*在精神上*遵循[语义化版本(Semantic Versioning)](http://semver.org/):
- "MAJOR(主版本)"更新:改变了某学科内部所学的主题
- "MINOR(次版本)"更新:更换了课程但没有改变主题
- "PATCH(修订)"更新:美观性或非实质性增删,或为优化进阶路径而调整课程顺序

## [8.0.0] 2017-11-01
### 新增
- extras/readings:《The System Design Primer》
- extras/readings:《Category Theory for Programmers: The Preface》
- extras/readings:《Programming Languages: Application and Interpretation》
- extras/readings:《Programming and Programming Languages》
- CONTRIBUTING:贡献者指南页面新增"学习 Git"小节
- 核心数学:新增《Essence of Linear Algebra》作为《Linear Algebra: Foundations to Frontiers》的先修课程

### 更新
- 《Introduction to Mathematical Thinking》移至 extras/courses
- 《Hack the Kernel》(ops-class)从高级系统移入核心系统
- 核心系统:《Operating Systems: Three Easy Pieces》不再是必修,改为《Hack the Kernel》的配套教材推荐
- 核心理论:斯坦福算法课的托管平台由 Coursera 换成 Lagunita,因为 Coursera 使用暗黑模式诱导用户付费

## [7.2.2] 2017-07-02
### 新增
- 《Haskell Programming from First Principles》一书,作为学习 Haskell 的付费替代资源
- extras/readings 收录《Think Python》
- 在相关课程下补充 FAQ 条目和链接
- extras/readings 收录《Category Theory: A Gentle Introduction》

## [7.2.1] 2017-05-14
### 更新
- 计算机网络课程的预计完成时间应为 8 周
- 修复拼写错误

### 新增
- [extras/courses](extras/courses.md) 收录 Introduction to Haskell 课程

## [7.2.0] 2017-04-28
### 新增
- 软件测试课程
- 斯坦福 Lagunita 的《Algorithms: Design and Analysis》链接
- 补充 MIT 单变量微积分课程中参数方程与极坐标小节的链接,为多变量微积分做好衔接

## [7.1.2] 2017-04-22
### 更新
- 在项目区(Plojects)介绍中添加 Mega Project List 链接

## [7.1.1] 2017-04-11
### 更新
- 发布前的最后打磨

## [7.1.0] 2017-04-10
### 更新
- 回滚了编程语言课程的一次格式调整

### 新增
- 可靠分布式算法系列课程
- 全新的计算机导论课程

## [7.0.2] 2017-03-30
### 更新
- 将可选的在线学习课程移至 extras/courses 的新小节
- 将备选的计算机体系结构课程移至 extras/courses

### 新增
- 高级应用下新增 Scala 专项课程

### 移除
- 必读书目只保留一个选择,简化课程体系

## [7.0.1] 2017-03-11
### 更新
- 修复 Bradfield DIY 计算机科学页面的链接

### 新增
- 微积分一(Calculus One)课程下添加勘误表和课程推进建议的链接
- extras 下的可选课程:
  - Strang 的线性代数课程
  - 伯克利《Structure and Interpretation of Computer Programs》
- extras 下的选读书目:
  - Van Roy 的高级编程书籍
  - P&H 的计算机体系结构书籍
  - Skiena 的算法书籍
  - Strang 的线性代数书籍
  - 《Database Management Systems》
  - Tarr 关于创建领域专用语言的书
  - 多位作者关于分布式系统的文章

## [7.0] 2017-03-09
课程结构全面改版

### 更新
- 澄清贡献者指南并拆分为独立文件
- 从多个学科精简为四个学科、下设多个主题
- 将 free-books.md 与 paid-books.md 合并为 readings.md
- 将 free-courses.md 与 paid-courses.md 合并为 courses.md
- 用新版《How to Code》(软件开发 MicroMasters)替换旧版
- 用斯坦福算法课替换普林斯顿算法课(后者移至[备选课程](extras/courses.md))

### 新增
- 为所有课程标注先修要求
- 明确要求:学科/主题要求与项目要求
- Haskell、Prolog、操作系统的必读书目
- 课程:Dan Grossman 的《Programming Languages》
- 课程:《From Nand to Tetris》
- 选修:《Intro to Parallel Programming》
- 选修:《LAFF: Programming for Correctness》
- 选修:《Introduction to Mathematical Thinking》
- 选修:《Electricity and Magnetism》
- 选修:MIT《Computation Structures》
- 选修:《Multivariable Calculus》
- 选修:ops-class.org
- 选修:《Automata Theory》
- 选修:《Introduction to Logic》
- 选修:《Computational Geometry》
- 选修:《Formal Concept Analysis》
- 选修:《Game Theory》
- 选修专项:
  - 机器人
  - 数据挖掘
  - 大数据
  - 物联网
  - 云计算
  - 全栈 Web 开发
  - 数据科学
- 进阶专项:
  - 《Mastering Software Development in R》
  - 人工智能工程师
  - 机器学习工程师
  - 网络安全
  - Android 开发者

### 移除
- 清理大量失效链接和过时课程
- 取消逐门课程的项目要求
- 课程:《Object-Oriented Programming in Java》
- 课程:《Functional Programming in Scala》
- 课程:《Computer Architecture》(保留为脚注)
- 课程:《Intro to Theoretical Computer Science》
- 课程:《Software Processes and Agile Practices》
- 课程:《Operating Systems & System Programming》
- 课程:《Introduction to Cyber Security》
- 课程:《Parallel Computer Architecture and Programming》
- 课程:《UX Design for Mobile Developers》

## [6.0] 2016-10-09
### 更新
- 将微积分一(Calculus One)前移,与《Mathematics for Computer Science》同步学习
- 改进"课程顺序"部分的文字

### 新增
- 为新版课程体系创建公开的 Trello 看板
- 在"如何使用本指南"中新增"如何跟踪和展示你的进度"小节
- 添加 PROJECTS.md 文件
- 将课程体系的各章节复制到 PROJECTS.md

### 移除
- 移除"下一步目标"小节
- 移除对 OSSU 网页应用的引用

---

> 📝 **译注**:以上为核心章节翻译(版本说明、语义化版本规则,以及 v6.0–v8.0.0 的主要变更)。更早的 v1.0.0–v5.1.0(2015-10 至 2016-08)为逐条课程链接修复与课程增删记录,细节繁多,此处未逐条翻译,完整内容请见[英文原版 CHANGELOG](https://github.com/ossu/computer-science/blob/master/CHANGELOG.md)。
