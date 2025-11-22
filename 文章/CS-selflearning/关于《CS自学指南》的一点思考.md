# 从项目中学习
## 第一阶段：新手入门
**条件分析**
只会基本的知识点，难以进行大型项目，语言C/C++，python
**应该掌握的知识点:**
- 基础编程语法（变量、循环、函数、类）
- 基本数据结构（数组、链表、栈、队列、哈希表）
- 基础算法（排序、搜索）
### **可行的实践项目:**
- [ ] **搭建个人博客网站或构建 To-Do List应用:**
    - **应用理论:** 面向对象编程（将博客文章或待-办事项抽象为对象）、数据结构（使用列表或数组存储条目）和文件操作（保存和读取数据）的绝佳项目。
    - **意义:** 熟悉后端开发的基本流程。
- [ ] **简单的命令行工具:**
    - **应用理论:** 例如，开发一个能分析文本文件词频的工具，可以锻炼你对哈希表（用于存储单词和频率）和文件I/O的应用能力。
    - **现实意义:** 许多开发工作都离不开命令行。熟悉命令行参数解析、标准输入输出，是成为高效工程师的基础。
- [ ]  **经典小游戏（如贪吃蛇、俄罗斯方块）:**
    - **应用理论:** 游戏开发是应用数据结构（如用二维数组表示游戏棋盘）和算法（游戏逻辑、碰撞检测）的趣味方式。
    - **现实意义:** 能够锻炼你的逻辑思维和代码组织能力，并让你初步接触图形用户界面（GUI）编程。

### **资源:**
- GitHub上有大量适合新手的开源项目，例如 "HelloGitHub" 和 "project-based-learning" 等仓库，提供了丰富的入门级项目创意和源码。
----

## **第二阶段：渐入佳境**
**条件分析**
此时可以进行一些更为复杂的项目了
### **操作系统与计算机系统**
**应该掌握的知识点:**
- 进程与线程管理
- 内存管理（虚拟内存、分页）
- 文件系统
- 并发与同步（锁、信号量）
#### **实践项目建议:**
- [ ] **实现一个简单的Shell:**
    - **应用理论:** 这个项目能让你深入理解进程创建（`fork`）、程序执行（`exec`）、管道（`pipe`）和I/O重定向等操作系统核心概念。
    - **现实意义:** 让你从用户和实现者的双重角度理解操作系统的交互方式，这对于进行系统级编程和性能调优至关重要。
- [ ] **多线程Web服务器或聊天应用:**
    - **应用理论:** 这是实践并发编程的最佳选择。你需要处理多个客户端的并发请求，并使用锁等机制来避免竞态条件，保护共享数据。
    - **现实意义:** 高并发处理是现代后端服务的核心挑战之一。拥有这方面的实践经验会让你在求职中极具竞争力。
### **计算机网络**
**应该掌握的知识点:**
- TCP/IP协议栈（特别是TCP和HTTP）
- Socket编程
- 网络分层模型
#### **实践项目建议:**
- [ ]  **实现一个简单的HTTP代理服务器:**
    - **应用理论:** 你需要解析HTTP请求和响应，并通过Socket在客户端和目标服务器之间转发数据。这能让你对HTTP协议和TCP连接有更深刻的认识。[3](https://github.com/iseesaw/ComputerNetwork)
    - **现实意义:** 理解网络代理和底层通信原理，有助于你未来进行网络调试、性能优化和构建分布式系统。
- [ ] **基于TCP的简易文件传输工具:**
    - **应用理论:** 练习Socket编程，理解客户端-服务器（C/S）架构，并处理数据传输中的分包、粘包等问题。
    - **现实意义:** 这是许多网络应用的基础，例如FTP、P2P下载等。
###  **数据库系统**
**应当掌握的知识点:**
- 关系型数据库模型（表、主键、外键）
- SQL语言
- 数据库索引（如B+树）
- 事务（ACID）
#### **实践项目建议:**
- [ ] **构建一个带有用户系统的Web应用（如电商网站、论坛）:**
    - **应用理论:** 你需要设计数据库表结构（ER图），并使用SQL进行复杂查询（如多表连接）。你还可以通过分析查询性能来理解索引的重要性。
    - **现实意义:** 数据库是绝大多数应用的“心脏”。 能够熟练使用数据库并进行基本的设计和优化，是初级软件工程师的必备技能。
- [ ]  **从零实现一个简单的KV存储引擎:**
    - **应用理论:** 这是一个极具挑战但回报丰厚的项目。你可以尝试实现基于哈希表或LSM树的存储，并加上预写日志（WAL）来保证持久性。
    - **现实意义:** 让你深入理解NoSQL数据库的内部工作原理，这在需要处理海量数据的今天尤为重要。
----

## **第三阶段：探索前沿领域**
### **条件分析**
此时已经可以轻松应对传统项目了，现在需要的使积极探索前沿领域（如AI，云计算等等），提高自身职业竞争力
### **项目建议:**
- **云计算与DevOps:**
    - **理论知识:** 学习Docker容器化技术和Kubernetes（K8s）编排工具，了解CI/CD（持续集成/持续部署）流水线。
    - **实践项目:** 将之前开发的Web应用进行容器化，编写Dockerfile，并尝试使用GitHub Actions或Jenkins建立一个简单的CI/CD流程，实现代码提交后自动构建和部署。
    - **现实意义:** 云原生和DevOps已成为现代软件开发的标准实践，是高效、可靠交付软件的保障。
- **人工智能与机器学习:**
    - **理论知识:** 学习机器学习基础，如线性回归、逻辑回归，并了解神经网络和深度学习的基本概念。
    - **实践项目:**
        - **情感分析:** 使用Python和Scikit-learn/TensorFlow等库，对电影评论或商品评论进行情感分类。
        - **图像识别:** 基于MNIST手写数字数据集，训练一个简单的卷积神经网络（CNN）来进行图像分类。
    - **现实意义:** AI正在渗透到各行各业，具备AI和机器学习基础知识的工程师将有更多机会参与到智能化应用的开发中。
----

## 如何展示项目：打造专业的“工程师名片”
1. **使用GitHub:** 项目代码托管在GitHub上，并认真编写`README.md`文件。在其中清晰地说明项目的功能、使用的技术、如何运行，以及在项目中遇到的挑战和解决方案。
2. **撰写技术博客:** 针对在项目中学到的关键知识点或解决的难题，撰写技术博客。
3. **构建个人作品集网站:** 创建一个简单的个人网站，展示项目、博客链接和简历。
----

# 构建高效的工作学习流
## 收集信息
- 筛选
	收集信息首先要对信息进行筛选，从中选取质量较高的信息。
	以知识的时效性和完整性出发 `源代码` > `官方文档` > `英文书籍` > `英文博客` > `中文博客
	学习一个知识点时先尽量选择质量更高的，信息损失较少的信息源，同时不妨参考多个信息源，让自己的理解更加全面准确。
- 收集
	跨端收藏网页：cubox
	收集小网站信息：RSS Reader(生成和发现）+Feedly（订阅）
- 格式转换
	目的:将收集到的信息转换为markdown或pdf格式，方便处理
	网页转markdown：简悦
	其他格式的电子书转pdf：calibre
## 处理信息
- 英文
	划词翻译：Quicker` + `沙拉查词
-  多媒体信息
	Language Reactor：导出油管和网飞视频字幕，同时附上中文翻译。
	Media Extended：笔记内跳转到视频指定时间进度
	Annotator：笔记内跳转到 pdf 原文与标注
- 笔记
	obsidian：基于本地，基于markdown，支持双链，插件生态丰富
## 回顾信息
Anki：有obsidian插件，使用该插件可以截取笔记的片段导出到 `Anki` 并变成一张卡片，卡片内也有跳转回笔记原文的链接
# CSer必备工具
## Vim
- 让你的整个开发过程手指不需要离开键盘，而且光标的移动不需要方向键使得你的手指一直处在打字的最佳位置。
- 方便的文件切换以及面板控制可以让你同时开发多份文件甚至同一个文件的不同位置。
- Vim 的宏操作可以批量化处理重复操作（例如多行 tab，批量加双引号等等）
- Vim 是很多服务器自带的命令行编辑器，当你通过 `ssh` 连接远程服务器之后，由于没有图形界面，只能在命令行里进行开发（当然现在很多 IDE 如 PyCharm 提供了 `ssh` 插件可以解决这个问题）。
- 异常丰富的插件生态，让你拥有世界上最花里胡哨的命令行编辑器。
## Emacs
- 只需要键盘就可以完成所有操作，大量使用快捷键，具有极高的编辑效率。
- 既可以在终端无图形界面的场景下使用，也可使用有图形界面的版本获得更现代、更美观的体验。
- 扩展性极为强大，不限制插件
- 对vim用户友好
## GIt&Github
- 高效版本控制
- 多人协作必备
- 参与开源社区和维护项目必备
## GNU Make&CMake
- 能让你在一个脚本里（即所谓的 `Makefile`）定义整个编译流程以及各个目标文件与源文件之间的依赖关系，并且只重新编译你的修改会影响到的部分，从而降低编译的时间。
- 大型项目必要
## LaTex
- 写论文必备
- 用户只需要关注写作的内容，而排版则完全交给软件自动完成。这让没有任何排版经验的普通人得以写出排版非常专业的论文或文章。
## Docker
- 容器化，消解配环境的障碍
- 节约时间
- 轻量化
##  Scoop
- 快速搭建开发环境
- 一键安装并管理常见的开发软件
## 其他实用工具
### **下载工具**
- [Sci-Hub](https://sci-hub.se/): Elbakyan 女神向你挥手，旨在打破知识壁垒的革命性网站。
- [Library Genesis](http://libgen.is/): 电子书下载网站。
- [Z-library](https://z-library.rs/): 电子书下载网站（在 [Tor](https://www.torproject.org/) 下运行较佳，[链接](http://loginzlib2vrak5zzpcocc3ouizykn6k5qecgj2tzlnab5wcbqhembyd.onion/)）。
- [Z-ePub](https://z-epub.com/): ePub 电子书下载网站。
- [PDF Drive](https://www.pdfdrive.com/): PDF 电子书搜索引擎。
- [MagazineLib](https://magazinelib.com/): PDF 电子杂志下载网站。
- [BitDownloader](https://bitdownloader.io/): 油管视频下载器。
- [qBittorrent](https://www.qbittorrent.org/download.php): BitTorrent 客户端。
- [uTorrent](https://www.utorrent.com/): BitTorrent 客户端。
- [全国标准信息公共服务平台](https://std.samr.gov.cn/)：各类标准查询和下载官方平台。
- [标准知识服务系统](http://www.standards.com.cn/)：检索与阅读所需标准。
- [MSDN, 我告诉你](https://msdn.itellyou.cn/): Windows 操作系统镜像下载站，也有许多其他软件的下载。

### **设计工具**

- [excalidraw](https://excalidraw.com/): 一款手绘风格的绘图工具，非常适合绘制课程报告或者 PPT 内的示意图。
- [tldraw](https://www.tldraw.com/): 一个绘图工具，适合画流程图，架构图等。
- [draw.io](https://app.diagrams.net/): 强大简洁的在线的绘图网站，支持流程图，UML 图，架构图，原型图等等，支持 Onedrive, Google Drive, Github 导出，同时提供离线客户端。
- [origamiway](https://www.origamiway.com/paper-folding-crafts-step-by-step.shtml): 手把手教你怎么折纸。
- [thingiverse](https://www.thingiverse.com/): 囊括各类 2D/3D 设计资源，其 STL 文件下载可直接 3D 打印。
- [iconfont](https://www.iconfont.cn/): 国内最大的图标和插画资源库，可用于开发或绘制系统架构图。
- [turbosquid](https://www.turbosquid.com/): 可以购买各式各样的模型。
- [flaticon](https://www.flaticon.com/): 可下载免费且高质量的图标。
- [标准地图服务系统](http://bzdt.ch.mnr.gov.cn/): 可以下载官方标准地图。
- [PlantUML](https://plantuml.com/zh/): 可以使用代码快速编写 UML 图。

### **编程相关**

- [sqlfiddle](http://www.sqlfiddle.com/): 一个简易的在线 SQL Playground。
- [sqlzoo](https://sqlzoo.net/wiki/SQL_Tutorial)：在线练习 sql 语句。
- [sqlable](https://sqlable.com/)：一个 SQL 工具网站（格式化器、验证器、生成器，SQL Playground）。
- [godbolt](https://godbolt.org/): 非常方便的编译器探索工具。你可以写一段 C/C++ 代码，选择一款编译器，然后便可以观察生成的具体汇编代码。
- [explainshell](https://explainshell.com/): 你是否曾为一段 shell 代码的具体含义感到困扰？manpage 看半天还是不明所以？试试这个网站！
- [regex101](https://regex101.com/): 正则表达式调试网站，支持各种编程语言的匹配标准。
- [typingtom](https://www.typingtom.com/lessons): 针对程序员的打字练习 / 测速网站。
- [wrk](https://github.com/wg/wrk): 网站压测工具。
- [gbmb](https://www.gbmb.org/): 数据单位转换。
- [tools](https://tools.fun/): 在线工具合集。
- [github1s](https://github1s.com/): 用网页版 VS Code 在线阅读 GitHub 代码。
- [visualgo](https://visualgo.net/en): 算法可视化网站。
- [DataStructureVisual](http://www.rmboot.com/): 数据结构可视化网站。
- [Data Structure Visualizations](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html): 数据结构与算法的可视化网站。
- [learngitbranching](https://learngitbranching.js.org/?locale=zh_CN): 可视化学习 git。
- [UnicodeCharacter](https://unicode-table.com/en/): Unicode 字符集网站。
- [cyrilex](https://extendsclass.com/regex-tester.html): 一个用于测试和可视化正则表达式的网站，支持各种编程语言标准。
- [mockium](https://softwium.com/mockium/): 生成测试数据的平台。

### **学习网站**

- [HFS](https://hepsoftwarefoundation.org/training/curriculum.html): 各类软件教程。
- [Shadertoy](https://www.shadertoy.com/): 编写各式各样的 shader。
- [comments-for-awesome-courses](https://conanhujinming.github.io/comments-for-awesome-courses/): 名校公开课评价网。
- [codetop](https://codetop.cc/home): 企业题库。
- [cs-video-courses](https://github.com/Developer-Y/cs-video-courses): 带有视频讲座的计算机科学课程列表。
- [bootlin](https://elixir.bootlin.com/linux/v2.6.39.4/source/include/linux): 在线阅读 Linux 源码。
- [ecust-CourseShare](https://github.com/tianyilt/ecnu-PGCourseShare): 华东师范大学研究生课程攻略共享计划。
- [REKCARC-TSC-UHT](https://github.com/PKUanonym/REKCARC-TSC-UHT): 清华大学计算机系课程攻略。
- [seu-master](https://github.com/oneman233/seu-master): 东南大学研究生课程资料整理。
- [菜鸟教程](https://www.runoob.com/): 计算机相关知识的简要的教程。
- [FreeBSD 从入门到跑路](https://book.bsdcn.org/): 一本 FreeBSD 的中文教程。
- [MDN Web Docs](https://developer.mozilla.org/zh-CN/docs/Learn): MDN 网络开发入门手册。
- [Hello 算法](https://www.hello-algo.com/): 动画图解、能运行、可提问的数据结构与算法快速入门教程。

### **百科网站 / 词典性质的网站**

- [os-wiki](https://wiki.osdev.org/Main_Page): 操作系统技术资源百科全书。
- [FreeBSD Documentation](https://docs.freebsd.org/en/): FreeBSD 官方文档。
- [Python3 Documentation](https://docs.python.org/zh-cn/3/): Python3 官方中文文档。
- [C++ Reference](https://en.cppreference.com/w/): C++ 参考手册。
- [OI Wiki](https://oi-wiki.org/): 编程竞赛知识整合站点。
- [Microsoft Learn](https://learn.microsoft.com/zh-cn/): 微软官方的学习平台，包含了绝大多数微软产品的文档。
- [Arch Wiki](https://wiki.archlinux.org/): 专为 Arch Linux 而写的 Wiki，包含了大量 Linux 相关的知识。
- [Qt Wiki](https://wiki.qt.io/Main): Qt 官方 Wiki。
- [OpenCV 中文文档](https://opencv.apachecn.org/#/): OpenCV 的社区版中文文档。
- [npm Docs](https://docs.npmjs.com/): npm 官方文档。

### **交流平台**

- [GitHub](https://github.com/): 许多开源项目的托管平台，也是许多开源项目的主要交流平台，通过查看 issue 可以解决许多问题。
- [StackExchange](https://stackexchange.com/): Stack Exchange 是由 181 个问答社区组成（其中包括 Stack Overflow）的编程社区。
- [StackOverflow](https://stackoverflow.com/): Stack Overflow 是一个与程序相关的 IT 技术问答网站。
- [Gitee](https://gitee.com/): 一个类似于 GitHub 的代码托管平台，可以在对应项目的 issue 里查找一些常见问题的解答。
- [知乎](https://www.zhihu.com/): 一个类似于 Quora 的问答社区，可以在其中提问，一些问答包含有计算机的知识。
- [博客园](https://www.cnblogs.com/): 一个面向开发者的知识分享社区，拥有一些常见问题的博客，正确率不能保证，请谨慎使用。
- [CSDN](https://blog.csdn.net/): 拥有一些常见问题的博客，正确率不能保证，请谨慎使用。

### **杂项**

- [tophub](https://tophub.today/): 新闻热榜合集（综合了知乎、微博、百度、微信等）。
- [feedly](https://feedly.com/): 著名的 RSS 订阅源阅读器。
- [speedtest](https://www.speedtest.net/zh-Hans): 在线网络测速网站。
- [public-apis](https://github.com/public-apis/public-apis): 公共 API 合集列表。
- [numberempire](https://zh.numberempire.com/derivativecalculator.php): 函数求导工具。
- [sustech-application](https://sustech-application.com/#/grad-application/computer-science-and-engineering/README): 南方科技大学经验分享网。
- [vim-adventures](https://vim-adventures.com/): 一款基于 vim 键盘快捷键的在线游戏。
- [vimsnake](https://vimsnake.com/): 利用 vim 玩贪吃蛇。
- [keybr](https://www.keybr.com/): 学习盲打的网站。
- [Awesome C++](https://cpp.libhunt.com/): 很棒的 C/C++ 框架、库、资源精选列表。
- [HelloGitHub](https://hellogithub.com/): 分享 GitHub 上有趣、入门级的开源项目。
- [Synergy](https://github.com/DEAKSoftware/Synergy-Binaries): 一套键鼠能控制多台电脑。
# 学会信息检索
碰到问题，记住第一件事是 **翻阅文档** ，不要一开始就直接搜索或者找人问，翻阅FAQ可能会快速找到答案。如果没有找到再去搜索。
信息检索实际上就是灵活运用搜索引擎中，方便快捷的搜到需要的信息，包括但不限于编程。
## 使用英文
编程中，最好使用英文搜索。原因主要有几点：
1. 英文资料质量比中文资料和其他语言资料高，英文通用性更好
2. 因为翻译问题，英文的名词比中文准确通用
3. 中文搜索中，分词系统不准会导致歧义
## 提炼关键词
我们需要提炼问题，确定我们到底需要解决什么问题。
越具体的问题，机器分词越可能出问题，所以最好是拆分关键字，使用词组或者断句来进行搜索。
## 替换关键字
将一些词替换为近义词或者同义词
## 高级搜索

普通搜索引擎一般都支持高级搜索，不过可能语法不同，一般通用的表示：

- 精准匹配： 精准匹配能保证搜索关键词完全被匹配上，一般是用双引号括起来
- 不包含关键字： 用 - 减号连接关键字，用于排除某些干扰词
- 包含关键字： 用 + 加号连接关键字
- 搜索特定文件类型： `filetype:pdf` 直接搜索 pdf 文件
- 搜索特定网址： `site:stackoverflow.com` 只搜索特定网站内的页面

一般可以参照网站说明，比如百度可以参照 [高级搜索](https://baike.baidu.com/item/%E9%AB%98%E7%BA%A7%E6%90%9C%E7%B4%A2/1743887?fr=aladdin) ，Bing 可以参照 [高级搜索关键字](https://help.bing.microsoft.com/#apex/bing/zh-CHS/10001/-1) 和 [高级搜索选项](https://help.bing.microsoft.com/apex/index/18/zh-CHS/10002)。

### **GitHub 的高级搜索**
可以直接用 [高级搜索页面](https://github.com/search/advanced) 进行搜索，也可以参照 [Github 查询语法](https://zhuanlan.zhihu.com/p/273766377) 进行查找，简单说几个:
- `in:name <关键字>` 仓库名称带关键字查询
- `in:description <关键字>` 仓库描述带关键字查询
- `in:readme <关键字>` README 文件带关键字查询
- `stars(fork): >(=) <数字> <关键字>` star 或 fork 数大于 (或等于) 指定数字的带关键字查询
- `stars(fork): 10..20 <关键词>` star 或 fork 数在 10 到 20 之间的带关键字查询
- `size:>=5000 <关键词>` 限定仓库大于等于 5000K 的带关键字查询
- `pushed(created):>2019-11-15 <关键字>` 更新 或 创建 日期在 2019 年 11 月 16 日之后的带关键字查询
- `license:apache-2.0 <关键字>` LICENSE 为 apache-2.0 的带关键字查询
- `language:java <关键词>` 仓库语言为 Java 的带关键字查询
- `user:<用户名>` 查询某个用户的项目
- `org:<组织名>` 查询某个组织的项目 这些可以混合使用，也可以先查找某一类的 awesome 仓库，然后从 awesome 库里找相关的资源，github 里有很多归纳仓库，可以先看看已有的收集，有时候会节省很多时间
## 更多技巧

使用中，去特定网站找一些问题：

- 如果是语言本身相关，比如 c++/Qt/OpenGL 如何实现什么功能，可以直接加上 `site:stackoverflow.com`
- 如果是具体的业务 / 开发环境或者软件相关，可以先在 BugList 、IssueList ，或者相关论坛里先找一下，比如 Qt 的问题就可以直接去 Qt 论坛，QGis 或者 GDAL 相关问题可以在 stackExchange 里去搜
- QQ 群也是一个提问的地方，但是需要你提的问题有意义，否则大部分人不会回你，而且 QQ 群回复并不及时。
- 知乎专栏、简书、博客园、 CSDN 中有大量中文笔记，这些都是别人嚼烂了的东西，基本是别人踩坑的经验
## 代码搜索

### 本地代码搜索
- ACK 或者 ACK2，老牌搜索工具，perl 写的
- The Silver Searcher c 实现的
- The Platinum Searcher go 实现的
- FreeCommander 自带的搜索，如果是固态硬盘速度还不错
- IDE 自带的，搜索有些时候并不太好用
### 开源代码搜索
- [Searchcode](https://searchcode.com/) 搜索开源代码，速度比较快
- [一行代码](https://www.alinecode.com/) 国产的，有些国产工具很好用






