#  **前言**
本教程的目的是提供GIt和GitHub的基本功能的教学，旨在带领读者在GIthub上创建第一个仓库，并学习如何推送本地文件变更到远程仓库。为保证知识的通用性以，本文先从命令行讲起，最后以vscode为例讲解带GUI的Git工具。

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
# **第二部分：解决国内网络问题 (关键步骤)**
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
---
# **第五部分：使用vscode快捷使用git**
vscode可以用GUI直接使用git的常用功能，比命令行要简单，记忆成本比较低，但是如果要使用高级功能还是要用命令行。

vscode的GUI默认有三个工作区，分别是REPOSITORIES(显示你在GitHub上的所有项目),CHANGES（显示发生变更的文件）,GRAPH（用时间线显示你对仓库做的操作）
在CHANGES区域，可以直接输入commit并提交，同时也可以轻松push到远程仓库。
## vscode中文件的git操作
例如：
直接在vscode中右键文件，出现的多个选项的功能
- Open Change：打开修改后的文件（高亮显示修改部分）
- Open File：打开修改后的文件（普通打开）
- Open File（HEAD）:打开当前分支最后一次提交的版本
- Discard Changes：移除修改
- Staged Changes：将文件纳入版本控制
其余选项都是字面意思
----
# 第六部分：git常用命令速查
## 基础配置

|命令|说明|
|---|---|
|`git config --global user.name "你的姓名"`|设置全局用户名|
|`git config --global user.email "你的邮箱"`|设置全局邮箱|
|`git config --list`|查看所有配置|

## 创建与克隆

|命令|说明|
|---|---|
|`git init`|在当前目录初始化新仓库|
|`git clone <仓库URL>`|克隆远程仓库到本地|

##  查看状态与历史

|命令|说明|
|---|---|
|`git status`|查看工作区和暂存区状态|
|`git log`|查看提交历史|
|`git log --oneline`|简洁格式查看历史|
|`git log --graph`|图形化显示分支历史|
|`git show <commit-id>`|查看特定提交的详细信息|
|`git diff`|查看未暂存的更改|
|`git diff --staged`|查看已暂存的更改|

##  添加与提交

|命令|说明|
|---|---|
|`git add <文件名>`|添加特定文件到暂存区|
|`git add .`|添加所有更改到暂存区|
|`git add -p`|交互式选择要暂存的更改|
|`git commit -m "提交信息"`|提交暂存区的更改|
|`git commit -am "提交信息"`|添加所有更改并直接提交（跳过 git add）|

##  撤销与恢复

|命令|说明|
|---|---|
|`git restore <文件名>`|撤销工作区的更改（Git 2.23+）|
|`git restore --staged <文件名>`|将文件从暂存区移回工作区|
|`git reset <commit-id>`|回退到指定提交（默认软重置）|
|`git reset --hard <commit-id>`|硬重置，丢弃所有更改|
|`git revert <commit-id>`|创建新的提交来撤销指定提交|

##  分支管理

|命令|说明|
|---|---|
|`git branch`|查看所有分支|
|`git branch <分支名>`|创建新分支|
|`git checkout <分支名>`|切换到指定分支|
|`git switch <分支名>`|切换到指定分支（Git 2.23+）|
|`git checkout -b <新分支名>`|创建并切换到新分支|
|`git switch -c <新分支名>`|创建并切换到新分支（Git 2.23+）|
|`git branch -d <分支名>`|删除分支|
|`git branch -D <分支名>`|强制删除分支|
|`git merge <分支名>`|合并指定分支到当前分支|

## 远程仓库操作

| 命令                          | 说明           |
| --------------------------- | ------------ |
| `git remote -v`             | 查看远程仓库信息     |
| `git remote add <名称> <URL>` | 添加远程仓库       |
| `git fetch <远程名>`           | 下载远程仓库更新但不合并 |
| `git pull <远程名> <分支名>`      | 下载并合并远程更改    |
| `git push <远程名> <分支名>`      | 推送本地提交到远程仓库  |
| `git push -u <远程名> <分支名>`   | 推送并设置上游分支    |

##  标签管理

|命令|说明|
|---|---|
|`git tag`|查看所有标签|
|`git tag <标签名>`|创建轻量标签|
|`git tag -a <标签名> -m "说明"`|创建带注释的标签|
|`git push <远程名> <标签名>`|推送标签到远程仓库|
|`git push <远程名> --tags`|推送所有标签到远程仓库|

##  清理与维护

|命令|说明|
|---|---|
|`git clean -n`|预览将被删除的未跟踪文件|
|`git clean -f`|删除未跟踪的文件|
|`git gc`|清理优化仓库|

##  实用技巧命令

| 命令                 | 说明           |
| ------------------ | ------------ |
| `git stash`        | 临时保存工作进度     |
| `git stash pop`    | 恢复最近的工作进度    |
| `git rebase <分支名>` | 变基操作         |
| `git bisect start` | 使用二分查找定位问题提交 |


----
