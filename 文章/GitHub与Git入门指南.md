#  **前言**
本教程的目的是提供GIt和GitHub的基本功能的教学，旨在带领读者在GIthub上创建第一个仓库，并学习如何推送本地文件变更到远程仓库。

---
#  **第一部分：入门准备**
在开始之前，我们需要先完成一些基础设置。
## **1. 理解 Git 与 GitHub**
-  **Git**: 一个安装在你电脑上的**软件**，如同代码的“时光机”，负责追踪文件的每一次修改。
- **GitHub**: 一个**网站服务**，如同存放 Git 时光机的“云端保险库”，用于同步、分享和协作。
**关系：** 本地用 Git 管理 -> 推送 (Push) 到 GitHub 网站备份和分享。
## **2. 注册 GitHub 账号并安装 Git**
- [ ] **注册账号**: 访问 [github.com](https://github.com/)，注册一个免费账号。
- [ ] **安装 Git**:
    - **Windows**: 访问 [git-scm.com](https://git-scm.com/download/win) 下载并安装。安装后，请使用 **Git Bash** 这个命令行工具。
    - **macOS**: 打开“终端 (Terminal)”，输入 `git --version`，如果未安装，系统会引导你安装。
## **3. 配置你的 Git 信息**
这是**至关重要的一步**，它决定了你提交代码时的“署名”。打开你的命令行工具 (Git Bash)，运行以下命令：
```bash
# 1. 访问你的 GitHub 邮箱设置页面：https://github.com/settings/emails
# 2. 勾选 "Keep my email addresses private" 和 "Block command line pushes that expose my email"
# 3. 复制页面上提供的格式为 `ID+username@users.noreply.github.com` 的匿名邮箱。
# 4. 在命令行中配置 Git
git config --global user.name "你的GitHub用户名"
git config --global user.email "你刚刚复制的GitHub匿名邮箱"
```

这样做的目的是保护你的真实邮箱不被公开在互联网上，避免收到垃圾邮件。

---
#  **第二部分：解决国内网络问题 (关键步骤)**
在国内使用 `git clone` 或 `git push` 时，你很有可能会遇到 `Connection was reset` 或 `Connection timed out` 等网络错误。这是因为网络环境（很有可能是GFW）对 GitHub 的 HTTPS 连接存在干扰。
**最佳解决方案是切换到更稳定、更专业的 SSH 协议。**（当然代理也是可以的，但是配置比较麻烦，因为给git必须要手动设置代理）
方法如下：
## **1. 生成 SSH 密钥**
- [ ] 在 Git Bash 中运行 `ls -al ~/.ssh`，检查是否存在 `id_rsa.pub` 文件。
- **如果存在**，跳到下一步。
- **如果不存在**，运行以下命令生成：
```bash
    ssh-keygen -t rsa -b 4096 -C "你的GitHub匿名邮箱"
```
接下来会提问两次，**连续按回车键**使用默认设置即可。
## **2. 在 GitHub 添加公钥**
- [ ] 复制你的公钥内容。在 Git Bash 中运行：
```bash
    cat ~/.ssh/id_rsa.pub
    # 将输出的一整长串 `ssh-rsa ...` 字符完整复制。
```
- [ ] 登录 GitHub -> 点击右上角头像 -> **Settings** -> **SSH and GPG keys** -> **New SSH key**。
- [ ] **Title**: 起一个名字，如 "My Laptop"。
- [ ] **Key**: 粘贴你复制的公钥内容。
- [ ]  点击 **Add SSH key**。
## **3. 测试 SSH 连接**
- [ ] 在 Git Bash 中运行：
```bash
ssh -T git@github.com
```
首次连接时，会询问 `(yes/no)`，输入 `yes` 并回车。如果看到 `Hi your-username! You've successfully authenticated...` 的欢迎信息，则代表连接成功。
**完成了以上项目，基本上不会有网络问题了

---
# **第三部分：第一个项目**

完整流程：在 GitHub 创建项目 -> 克隆到本地 -> 修改 -> 推送回 GitHub。
## **1. 在 GitHub 创建新仓库 (Repository)**
- [ ]  登录 GitHub，点击右上角 `+` -> **New repository**。
- [ ] **Repository name**: 给项目起个名字，如 `my-first-repo`。
- [ ]  **Description**: 写一句简单的描述。
- [ ]  **Public/Private**: 公开或私有，按需选择。
1. **强烈建议勾选以下三项**，让你的项目从一开始就规范化：
    - [ ]  ` Add a README file` (项目说明书)
    - [ ]  ` Add .gitignore` (忽略文件列表)，在下拉菜单中选择一个模板，如 `Python` 或 `Node`
    - [ ] `Choose a license` (许可证)，个人代码项目推荐选择 `MIT License`。
2. 点击 **Create repository**。
##  **2. 将项目克隆 (Clone) 到本地**
- [ ]  在刚创建的仓库页面，点击绿色的 **`<Code> `** 按钮。
- [ ]  **切换到 `SSH` 标签页**，复制那个以 `git@github.com:` 开头的地址。
- [ ] 在你的电脑上，打开命令行 (Git Bash)，`cd` 到一个你想要存放项目的文件夹（如桌面 `cd ~/Desktop`）。
- [ ] 运行 `git clone` 命令：
```bash
    git clone 你刚刚复制的SSH地址
    # 示例: git clone git@github.com:your-username/my-first-repo.git
```
##  **3. 本地修改与推送 **
- [ ] **进入项目文件夹**: `cd my-first-repo`
- [ ] **修改/创建文件**: 创建一个新文件 `hello.txt`，并写入 "Hello, World!"。
- [ ] **查看状态**: `git status` (会提示你有一个新文件)
- [ ]  **添加修改**: `git add .` (这个点 `.` 代表添加所有修改)
- [ ] **提交修改**: `git commit -m "Add hello.txt file"` (引号内是对本次修改的简要描述)
- [ ] **推送到 GitHub**: `git push`
现在，刷新 GitHub 仓库页面，就能看到 `hello.txt` 文件了。
---
# **第四部分：日常操作总结**
- **开始新工作前**: `git pull` (从 GitHub 拉取最新版本，保持同步)
- **完成修改后**:
    1. `git add .` (添加所有修改)
    2. `git commit -m "有意义的说明"` (创建本地存档)
    3. `git push` (推送到 GitHub)