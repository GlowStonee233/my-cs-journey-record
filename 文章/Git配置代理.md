# 前言
因为众所周知的原因，Git仓库在推送到GitHub上时有可能出现网络问题，即使ssh有时也不免遇到，本文旨在教学如何配置git的代理，达到一劳永逸的效果
# 常见错误信息
```bash
$ git pull --tags origin main ssh: connect to host github.com port 22: Connection refused fatal: Could not read from remote repository.
```
或者：
```bash
$ ssh -T git@github.com Connection reset by 20.205.243.160 port 443
```
# 准备工作

## 确认你的代理端口

首先需要知道你的代理软件监听的本地端口：

|代理软件|HTTP 端口|SOCKS5 端口|
|---|---|---|
|Clash|7890|7891|
|V2Ray|10808|10809|
|Shadowsocks|1080|1080|

**查看方法：**
- 打开代理软件界面，查找 "本地端口" / "监听端口"
- V2Ray 显示 `本地：[mixed:10808]` 表示端口是 `10808`
# 方案一：SSH 方式配置代理（推荐）

适用于仓库地址是 `git@github.com:xxx/xxx.git` 格式。

## 步骤 1：编辑 SSH 配置文件

```bash
nano ~/.ssh/config
```

### 步骤 2：添加以下内容

**Windows 用户：**
```
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
    ProxyCommand connect -H 127.0.0.1:10808 %h %p
```

**Mac/Linux 用户：**
```
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
    ProxyCommand nc -v -x 127.0.0.1:10808 %h %p
```

> ⚠️ 将 `10808` 替换为你的实际代理端口

## 步骤 3：测试连接
```bash
ssh -T git@github.com
```

成功会显示：
```
Hi 用户名! You've successfully authenticated, but GitHub does not provide shell access.
```

## 配置说明

|参数|说明|
|---|---|
|`Hostname ssh.github.com`|使用 GitHub 的 SSH 备用域名|
|`Port 443`|使用 443 端口避免 22 端口被封|
|`ProxyCommand`|指定代理命令|
|`-H`|使用 HTTP 代理|
|`-S`|使用 SOCKS5 代理|

---

# 方案二：HTTPS 方式配置代理

适用于仓库地址是 `https://github.com/xxx/xxx.git` 格式。

## 步骤 1：切换远程地址为 HTTPS

```bash
# 查看当前远程地址
git remote -v

# 修改为 HTTPS 格式
git remote set-url origin https://github.com/用户名/仓库名.git
```

### 步骤 2：配置 Git 全局代理

```bash
# 设置代理
git config --global http.proxy http://127.0.0.1:10808
git config --global https.proxy http://127.0.0.1:10808
```

### 步骤 3：验证配置
```bash
# 查看配置
git config --global --get http.proxy
git config --global --get https.proxy
```

### 取消代理（如需要）
```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```
---
## 方案三：仅对 GitHub 配置代理

如果不想全局代理，只针对 GitHub：
```bash
git config --global http.https://github.com.proxy http://127.0.0.1:10808
```

取消：
```bash
git config --global --unset http.https://github.com.proxy
```

---

# 常见问题排查

## 问题 1：`connect` 命令找不到

Windows Git Bash 通常自带，如果没有，尝试使用完整路径：
```bash
ProxyCommand /mingw64/bin/connect -H 127.0.0.1:10808 %h %p
```
### 问题 2：提示主机真实性无法确认
```bash
Are you sure you want to continue connecting (yes/no)?
```
输入 `yes` 回车即可，这是正常的首次连接确认。
### 问题 3：Connection refused
检查代理软件是否正在运行，端口是否正确。
### 问题 4：Broken pipe
将 `-S`（SOCKS5）改为 `-H`（HTTP）：
```
ProxyCommand connect -H 127.0.0.1:10808 %h %p
```

---

## 最终配置总结

### SSH 方式（~/.ssh/config）
```
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
    ProxyCommand connect -H 127.0.0.1:10808 %h %p
```

### HTTPS 方式
```bash
git config --global http.proxy http://127.0.0.1:10808
git config --global https.proxy http://127.0.0.1:10808
```

---

## 注意事项

1. **保持代理开启** - 配置代理后，使用 Git 时需要保持代理软件运行
2. **端口要正确** - 务必确认你的代理软件实际监听端口
3. **推荐 SSH 方式** - 配置一次永久生效，无需每次输入密码

---
