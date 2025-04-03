---
title: M4 Air 已经到货-所以我整理了我 Mac 上的应用程序
author: 
created: 2025-03-28T05:13:48
modified: 2025-03-28T17:14:11
source: https://www.v2ex.com/t/1121779
type: archives-web
---

> 在隔壁发了，这边同步发一下吧

对 MacOS 的应用我秉持这样的原则：

- 第一顺位 Web 版，比如：Discord 、Slack 、Telegram 、Spotify
- 第二顺位 App Store 版
- 第三顺位 Homebrew
- 除此之外不安装

其中 Web 版不需要更新，App Store 会自动更新，Homebrew 只需要每天执行下命令

```
brew update && brew upgrade && brew cu -a -y && brew cleanup 
```

但 App Store 有时候会好几天才能自动更新上，这不能忍，安装上 [mas](https://github.com/mas-cli/mas/ "https://github.com/mas-cli/mas/") 用命令行触发强制更新，再加上鼠须管的词库更新和 alias ，下面就是我的总命令了

```
alias up="brew update && brew upgrade && brew cu -a -y && brew cleanup && mas upgrade && ~/plum/rime-install iDvel/rime-ice:others/recipes/full" 
```

#### 🛠 系统拓展

---

- **[Homebrew](https://brew.sh/ "https://brew.sh/")** - macOS 包管理工具，用于安装/升级开发环境依赖
- **[DisplayLink Manager](https://www.displaylink.com/ "https://www.displaylink.com/")** - 多屏扩展驱动工具
- **[Logi Options+](https://www.logitech.com/ "https://www.logitech.com/")** - 罗技键鼠高级配置工具
- **[Raycast](https://www.raycast.com/ "https://www.raycast.com/")** - 快速启动与工作流增强工具
- **[Ice](https://icemenubar.app/ "https://icemenubar.app/")** - 状态栏管理工具（ Bartender 替代品）
- **[The Unarchiver](https://theunarchiver.com/ "https://theunarchiver.com/")** - 多格式解压工具

#### 🔐 安全工具

---

- **[1 Password](https://1password.com/ "https://1password.com/")** - 跨平台密码管理器
- **[YubiKey Manager](https://www.yubico.com/support/download/yubikey-manager/ "https://www.yubico.com/support/download/yubikey-manager/")** - FIDO 2 硬件密钥管理
- [Cryptomator](https://cryptomator.org/ "https://cryptomator.org/") - 开源文件加密工具
    - 工作流：本地文件加密 → 自动同步至 Dropbox 实现安全云存储

#### 📁 文件管理

---

- **[Dropbox](https://www.dropbox.com/ "https://www.dropbox.com/")** - 加密存储（通过 Cryptomator 加密敏感文件后同步）
- **[OneDrive](https://onedrive.live.com/ "https://onedrive.live.com/")** - 主力文件分享平台

#### 🌏 网络工具

---

- **[Surge](https://nssurge.com/ "https://nssurge.com/")** - 网络代理/试调工具
- **[Tailscale](https://tailscale.com/ "https://tailscale.com/")** - 组建私有网络，连接 NAS/笔记本/VPS 实现远程访问
- **[Firefox](https://www.mozilla.org/en-US/firefox/ "https://www.mozilla.org/en-US/firefox/")**（主浏览器）
    - 核心扩展：
        - Vimium - 键盘操作浏览器
        - 1 Password - 密码管理
        - HTTPS Everywhere - 强制 HTTPS 连接
        - Cookie AutoDelete - 自动清理 Cookie
        - NoScript - 默认禁用 JavaScript, 手动放行
        - Decentraleyes - 拦截 CDN 请求
        - AdGuard AdBlocker - 广告拦截
        - UBlock Origin - 广告拦截与隐私保护
        - Privacy Badger - 智能反追踪
        - ClearURLs - 移除 URL 追踪参数
        - CanvasBlocker - 屏蔽浏览器指纹
        - WebRTC Leak Shield - 防止 IP 泄漏
        - Kagi Search - 默认搜索引擎
        - Tampermonkey - 加载自定义脚本
    - 内容增强：
        - Enhancer for YouTube™ - 优化 YouTube 体验
        - SocialFocus - 屏蔽社交媒体干扰
        - Immersive Translate - 沉浸式翻译
        - RSSHub Radar - RSS 生成工具
        - Medium Parser - 解除部分 Medium 付费墙
    - 信息管理：
        - Archive Page - 查看付费墙/失效网页
        - Obsidian Web Clipper - 保存文章到 Obsidian
        - Raindrop. Io - 网页书签管理
        - Readwise Highlighter - 文章稍后读功能
- **[Brave](https://brave.com/ "https://brave.com/")**（调试浏览器）
    - 核心扩展：
        - Vimium - 键盘操作浏览器
        - 1 Password - 密码管理
        - HTTPS Everywhere - 强制 HTTPS 连接
        - Cookie AutoDelete - 自动清理 Cookie
        - NoScript - 默认禁用 JavaScript, 手动放行
        - Decentraleyes - 拦截 CDN 请求
        - AdGuard AdBlocker - 广告拦截
        - UBlock Origin - 广告拦截与隐私保护
        - Privacy Badger - 智能反追踪
        - ClearURLs - 移除 URL 追踪参数
        - CanvasBlocker - 屏蔽浏览器指纹
        - WebRTC Leak Shield - 防止 IP 泄漏
        - Kagi Search - 默认搜索引擎
        - Tampermonkey - 加载自定义脚本
    - 开发者工具：
        - Wappalyzer - 网站技术栈分析
        - React Developer Tools - React 调试
        - Vue. Js devtools - Vue 调试
        - CSS Peeper - 提取网页样式
        - JSON Formatter - JSON 数据格式化
    - API 相关：
        - Postman / RestClient - API 测试
        - Advanced REST client - REST 接口调试
    - Web 3 生态：
        - MetaMask - 数字钱包
        - MetaDock - 区块链浏览器增强
        - Web 3 Debug - 智能合约调试
        - IPFS Companion - 查看 IPFS 网页
        - Eth Gas Reporter - Gas 费用监控

#### 🧰 工作工具

---

- **效率工具**
    - **[Bob](https://bobtranslate.com/ "https://bobtranslate.com/")** × **[PopClip](https://pilotmoon.com/popclip/ "https://pilotmoon.com/popclip/")** - 划词翻译黄金组合（选中文本自动触发翻译）
    - **[Things 3](https://culturedcode.com/things/ "https://culturedcode.com/things/")** - 全平台待办事项管理系统（ GTD 工作流实践）
    - **[Spark](https://sparkmailapp.com/ "https://sparkmailapp.com/")** - 智能邮件客户端（支持多账户统一收件箱）
- **知识管理**
    - **[Calibre](https://calibre-ebook.com/ "https://calibre-ebook.com/")** - 电子书元数据管理（支持格式转换/云端同步）
    - **[Zotero](https://www.zotero.org/ "https://www.zotero.org/")** - 学术文献管理系统（ PDF 标注/引文自动生成）
    - **[Eagle](https://en.eagle.cool/ "https://en.eagle.cool/")** - 设计素材资产管理（支持 PSD/Sketch 文件预览）
    - **[Obsidian](https://obsidian.md/ "https://obsidian.md/")** - 双链笔记核心系统
        - Attachment Management 自动附件归档
        - Calendar 日历功能
        - Commander 自定义按键
        - Copilot for Obsidian AI 助手
        - Dataview Obsidian 最强数据库
        - Easy Typing 自动规范化格式
        - Excaildraw 最强白板
        - Execute Code 显示代码高亮
        - Local image 把网络文件同步到本地
        - Quick Latex 数学公式
        - QuickAdd 快速添加模版
        - Quick Explorer 显示文件路径
        - Readwise Official 同步 Readwise
        - Templates 模版增强
        - Tag Wrangler 标签批量管理
        - Obsidian Git 同步至 Github
        - Float search 更好的搜索视图
        - Better search view 更好的搜索视图
    - **[Anki](https://apps.ankiweb.net/ "https://apps.ankiweb.net/")** - 间隔重复记忆系统（内置语言学词频数据库）
    - **[Cherry Studio](https://www.cherrypicked.ai/ "https://www.cherrypicked.ai/")** - 多模型 AI 交互终端
- **创作套件**
    - **[Screen Studio](https://www.screen.studio/ "https://www.screen.studio/")** - 4 K 级操作录屏工具（自动镜头追踪/动态缩放）
    - **[Affinity Photo](https://affinity.serif.com/ "https://affinity.serif.com/")** - 专业级 RAW 处理与 LUT 调色（替代 Photoshop ）
    - **[Final Cut Pro](https://www.apple.com/final-cut-pro/ "https://www.apple.com/final-cut-pro/")** - 主要剪辑工具

#### 👨🏻‍💻 开发工具

---

- **编辑器**
    - **[Cursor](https://www.cursor.com/ "https://www.cursor.com")**
        - **Vim** - 使用习惯了，必装
        - **GitHub Copilot** - AI 代码补全核心插件
        - **GitLens** - Git 增强工具
        - **ES 7+ React/Redux/React-Native snippets** - React 代码快捷提示插件
        - **Solidity + HardHat** - Solidity 本地编写的语法高亮与格式化支持，HardHat 支持
        - **rust-analyzer** - 实时编译和分析 Rust 代码，提示代码中的错误，并对类型进行标注
        - **rust test lens** - 单元测试增强工具
        - **crates** - 分析当前项目的依赖是否是最新版本
        - **go** - Go 语言环境支持
        - **Prettier** - 代码格式化器
        - **ESLint** - 代码质量检查
        - **Thunder Client** - API 调试客户端
        - **Beancount** - 纯文本记账系统
        - **WakaTime** - 开发行为追踪器（精确到 IDE 窗口的编码耗时统计）
    - **[Xcode](https://developer.apple.com/xcode/ "https://developer.apple.com/xcode/")**
        - **GitHub Copilot** - AI 代码补全核心插件
- **终端**
    - **[Warp](https://www.warp.dev/ "https://www.warp.dev/")** - 支持 AI 提示
        - Oh-my-zsh
        - Homebrew
        - Fnm + node + pnpm
        - Pyenv + python + pip
        - Goenv + go
        - Rustup + rust + cargo
- **服务器管理**
    - **SSH** - 远程连接协议（ Warp 集成）
    - **[Termius](https://termius.com/index.html "https://termius.com/index.html")** - 跨平台 SSH 客户端（云同步/SFTP 传输）
    - [**ServerCat](https://servercat.app/ "https://servercat.app/")** - 服务器监控仪表盘（资源使用可视化）
- **数据库管理**
    - **[TablePlus](https://tableplus.com/ "https://tableplus.com/")** - 多数据库客户端（ MySQL/PostgreSQL/Redis GUI ）
    - **[Medis](https://getmedis.com/ "https://getmedis.com/")** - Redis 管理工具（集群监控/键值操作）
- **接口调试**
    - **[RapidAPI](https://paw.cloud/ "https://paw.cloud/")** - 主力接口调试工具
- **容器**
    - **[OrbStack](https://orbstack.dev/ "https://orbstack.dev/")** - 轻量级容器运行时（ Docker 替代方案）
- **版本控制**
    - **Git** - 分布式版本控制系统
        - [czg](https://cz-git.qbb.sh/zh/cli/ "https://cz-git.qbb.sh/zh/cli/")，交互式规范化提交信息
        - [git-chglog](https://github.com/git-chglog/git-chglog "https://github.com/git-chglog/git-chglog")，用来自动生成格式化 CHANGELOG
        - [git-delta](https://github.com/dandavison/delta "https://github.com/dandavison/delta")，git 语法输出语法高亮工具
    - **本地 AI**
        - **[Ollama](https://ollama.com/ "https://ollama.com/")** - 本地大模型运行框架（ Llama 3/CodeLlama 支持）

#### 🎸 影音娱乐

---

- **[Downie 4](https://software.charliemonroe.net/downie/ "https://software.charliemonroe.net/downie/")** - 多媒体抓取工具（ YouTube/Bilibili 多平台支持）
- **[IINA](https://iina.io/ "https://iina.io/")** - 现代媒体播放器（ MPV 内核/硬件解码加速）
- **[Infuse](https://firecore.com/infuse "https://firecore.com/infuse")** - 多协议流媒体播放器（ NAS 挂载/杜比全景声支持）