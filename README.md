
# Lade CLI 多功能管理脚本
https://www.youtube.com/watch?v=RL2lFf0ymYI

https://gist.github.com/lym377/6c37ca6bf207a94e355a45dab1e5d9c7#file-gistfile1-txt

这是一个跨平台的 Bash 和 PowerShell 脚本，旨在简化 Lade 应用的部署和日常管理。它自动化了 Lade CLI 的安装、应用部署、查看、删除和日志管理等常用操作，让你的开发和运维工作更加高效。

-----

## 主要功能

  * **Lade CLI 自动安装：** 自动检测并安装最新版本的 Lade CLI 工具（支持 Linux、macOS 和 Windows）。
  * **应用部署：** 快速部署 Ladefree 应用到 Lade 平台，支持创建新应用或更新现有应用。此过程不依赖本地 Git，直接通过 ZIP 包下载部署。
  * **应用管理：**
      * 查看所有已部署的 Lade 应用。
      * **删除**指定的 Lade 应用 (`lade apps remove`)。
      * 查看应用实时日志。
  * **登录状态刷新：** 检查并提示你刷新 Lade 登录会话。
  * **跨平台支持：** 提供 Bash 和 PowerShell 两个版本，兼容主流操作系统。

-----

## 如何使用

你可以根据你的操作系统选择使用 Bash 或 PowerShell 脚本。

### Bash 版本 (Linux / macOS)

1.  **一行命令运行脚本：**
    直接在终端中运行以下命令即可自动下载并执行脚本。

    ```bash
    bash <(curl -l -s https://raw.githubusercontent.com/byJoey/ladefree/refs/heads/main/install.sh)
    ```


2.  **脚本运行步骤：**

      * 脚本会首先检查并安装 **Lade CLI**。你可能需要输入 `sudo` 密码来完成安装。
      * 安装完成后，将显示主菜单，你可以根据提示选择相应操作。

### PowerShell 版本 (Windows)

1.  **以管理员身份运行 PowerShell：**
    为了确保 Lade CLI 能够正确安装到系统路径，并执行其他需要权限的操作，**强烈建议以管理员身份运行 PowerShell**。

2.  **一行命令运行脚本：**
    **重要安全提示：** 以下命令使用了 `-ExecutionPolicy Bypass` 参数，它会绕过 PowerShell 的执行策略，允许运行任何脚本。**请确保你完全信任此脚本的来源，否则可能存在安全风险。**

    打开 PowerShell 并运行以下命令：

    ```powershell
    Invoke-WebRequest -Uri "https://raw.githubusercontent.com/byJoey/ladefree/main/install.ps1" -OutFile "$env:TEMP\install.ps1"; PowerShell -ExecutionPolicy Bypass -File "$env:TEMP\install.ps1"; Remove-Item "$env:TEMP\install.ps1" -ErrorAction SilentlyContinue
    ```

      * 此命令将脚本下载到临时文件夹。
      * 然后使用 `-ExecutionPolicy Bypass` 参数执行该脚本。
      * 最后，它会清理临时下载的脚本文件。

3.  **脚本运行步骤：**

      * 脚本会首先检查并安装 **Lade CLI**。在安装过程中，你可能会看到权限提升请求，请允许。
      * 安装完成后，将显示主菜单，你可以根据提示选择相应操作。

-----

一、注册验证账号
1.注册  官方网站lade.io
2.在github上个建立 一个gist
3.点击官网live chat 进行验证，按提示提供注册邮箱及gist链接
过一会，客服就会验证通过
二、下载app并修改设置
我用的是eooce大佬的singbox nodejs
地址：https://github.com/eooce/Sing-box
1.下载软件包，并将其中的nodejs文件夹中三个文件复制出来
2.用文本编辑器打开start.sh
编辑  argo 域名、json、端口、节点名称等信息，保存。
可用fscarmen大佬的ArgoX  Cloudflare Json 生成网轻松获取: https://fscarmen.cloudflare.now.cc
三、下载官网的lade连接程序
如果是windows则可将lade.exe扔进windows系统文件夹方便调用,如果觉得有安全风险，完成设置后删除即可

1.登入lade
lade login
输入注册邮箱、网站密码
用cd命令切换到nodejs文件夹下


2创建lade 应用，假设zxcs是应用名称，可随意修改
lade apps create zxcs
3. 部署lade 应用, 名字和上面保持一致
lade deploy --app zxcs

4 等一会儿，查看日志，节点信息在日志中
lade logs -a zxcs
5.可以查看应用运行状态
lade apps show zxcs


-----
## 感谢老王的notejs https://github.com/eooce

## 作者

  * **Joey**
      * 博客: [joeyblog.net](https://joeyblog.net)
      * Telegram 群: [https://t.me/+ft-zI76oovgwNmRh](https://t.me/+ft-zI76oovgwNmRh)

-----

## 许可

此项目根据 MIT 许可证发布 - 详情请参阅 [LICENSE](https://www.google.com/search?q=LICENSE) 文件。

-----
