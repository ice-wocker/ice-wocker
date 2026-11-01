<div align="center">

<img src="https://github.com/ice-wocker.png" width="112" alt="ice-wocker" />

# 嗨，我是冰块制造机 🧊

**零依赖 · 单文件 · 极小体积 · 把 AI 塞进手机**

*Tiny, dependency-free Android tools and on-device AI — offline first.*

[![关注](https://img.shields.io/github/followers/ice-wocker?label=%E5%85%B3%E6%B3%A8&color=FF5A2D&style=flat)](https://github.com/ice-wocker?tab=followers)
[![Java](https://img.shields.io/badge/Java-Android%20%E4%B8%BB%E5%8A%9B-007396?logo=openjdk&logoColor=white)](#%EF%B8%8F-%E4%BB%A3%E8%A1%A8%E4%BD%9C)
[![关键词](https://img.shields.io/badge/%E5%85%B3%E9%94%AE%E8%AF%8D-%E9%9B%B6%E4%BE%9D%E8%B5%96%20%C2%B7%20%E7%A6%BB%E7%BA%BF%20%C2%B7%20%E6%9E%81%E5%B0%8F%E4%BD%93%E7%A7%AF-8B5CF6)](#%F0%9F%A7%AD-%E6%88%91%E5%9C%A8%E6%84%8F%E7%9A%84%E5%87%A0%E4%BB%B6%E4%BA%8B)
[![License](https://img.shields.io/badge/License-MIT%20%2F%20GPL--3.0-3DA639)](https://github.com/ice-wocker?tab=repositories)

[![My Skills](https://skillicons.dev/icons?i=java,python,js,nodejs,shell,androidstudio,gradle)](https://skillicons.dev)

[代表作](#%EF%B8%8F-%E4%BB%A3%E8%A1%A8%E4%BD%9C) · [全部项目](#%F0%9F%93%A6-%E5%85%A8%E9%83%A8%E9%A1%B9%E7%9B%AE) · [我在意的几件事](#%F0%9F%A7%AD-%E6%88%91%E5%9C%A8%E6%84%8F%E7%9A%84%E5%87%A0%E4%BB%B6%E4%BA%8B) · [找到我](#%F0%9F%A4%9D-%E6%89%BE%E5%88%B0%E6%88%91)

</div>

---

我造一些**零依赖、单文件、真免费**的小轮子，也顺手把大模型塞进手机里跑。

主力写 Android（纯 Java、单 dex、能不引依赖就不引），需要的时候也写 Cloudflare Workers（JavaScript）和 Shell。判断一个项目做得行不行，我习惯先看三件事：**安装包多大、有几个第三方依赖、断网还能不能用**。

这个账号下所有项目均为原创。下面每个可安装的项目都直接给了 APK 下载入口——**点了就能装，不用先读文档、不用配环境**。

## 🛠️ 代表作

### 🎙️ [iceScribe](https://github.com/ice-wocker/iceScribe) — 把手机变成一支离线录音笔

离线语音转写的 Android App，内置 whisper.cpp，全程本机推理，**不申请 INTERNET 权限**。

*Offline voice-transcription Android app with built-in whisper.cpp — inference stays on-device, no INTERNET permission.*

- 录音结束自动转写；**权限清单里没有 INTERNET**，录音和文字没有任何路径离开这台设备
- 纯 CPU 离线推理：边录边重采样成 16 kHz 单声道落盘，转写按段流式读取，**录一小时内存也不涨**
- 支持导入已有音频（m4a / mp3 / wav / ogg）、中/英/自动检测与翻译、历史记录、模型导入管理
- 零第三方依赖；APK 内含基础模型，**装完即用**，不用自己下模型
- ⬇️ [下载 APK](https://github.com/ice-wocker/iceScribe/releases/latest)

### 🧠 [ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser) — 魔搭模型库

魔搭模型库的轻量 Android 客户端，内置 llama.cpp 离线对话，外加一个**能动手的智能体**。

*A lightweight ModelScope client for Android — browse and search models, download GGUF, and chat offline via built-in llama.cpp with an agent that can run shell commands and search the web.*

- 浏览魔搭大模型（分页 / 搜索 / 排序 / 多维筛选），应用内下载 `.gguf`（断点续传 + 完整性校验）
- 内置 **llama.cpp**，**纯 CPU 离线推理**；arm64 编了多档指令集后端，运行时按芯片自动选档
- 对话页是个能动手的智能体：模型可自主调用手机终端、联网搜索、读写工作区文件、预览网页
- 中英双语（应用内可切），KV 量化 + 前缀复用；`docs/` 下 10 份手册同样中英各一份
- ⬇️ [下载 APK](https://github.com/ice-wocker/ModelScopeBrowser/releases/latest)

### 🌐 [iceBrowser](https://github.com/ice-wocker/iceBrowser) — Android 浏览器

纯 Java 编写的 Android 浏览器，零依赖、单 dex，带真多标签、广告拦截与阅读模式。

*A pure-Java Android browser — zero dependencies, single dex, with true multi-tab, ad blocking and reader mode.*

- 纯 Java / 单 dex / **0 第三方依赖**，体积按百 KB 计——不是几十 MB
- 真正的多 Tab，多个搜索引擎可切换，内置广告拦截 / 阅读模式 / 无痕模式
- ⬇️ [下载 APK](https://github.com/ice-wocker/iceBrowser/releases/latest) · `MIT`

### 📱 [iceLLM](https://github.com/ice-wocker/iceLLM) — 一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器

跑在 Android（Termux）上，装完就在局域网里得到一个本地大模型，完全离线。

*Turn your Android phone into an OpenAI-compatible local AI server with one command — available on your LAN, fully offline.*

```bash
curl -fsSL https://raw.githubusercontent.com/ice-wocker/iceLLM/main/ice-llm.sh | bash
```

- 自带 WebUI，同时暴露 `http://<手机IP>:8080/v1/chat/completions`——任何 OpenAI 客户端改个 `base_url` 就能用
- 支持 MiniCPM5 / Qwen2.5 / Qwen3；**完全离线**：不要 API Key、不上云、数据不出设备
- `MIT`

### 📄 [iceScan](https://github.com/ice-wocker/iceScan) — 随身扫描仪

离线文档扫描：拍一张自动找边、透视拉直、去阴影，多页合成 PDF，零权限零依赖不联网。

*Offline document scanner — snap a page to auto-detect edges, flatten and export multi-page PDFs, with zero permissions and zero dependencies.*

- **权限列表是空的**：拍照走系统相机、选图走系统文件选择器、导出用自带 `ContentProvider`，三件事都不要权限
- 手写单应矩阵求解 + 双线性反查采样；黑白档用 Bradley 自适应阈值（积分图，O(像素数)），阴影区不会被整片染黑
- ⬇️ [下载 APK](https://github.com/ice-wocker/iceScan/releases/latest)

### 🔒 [IceGuard](https://github.com/ice-wocker/IceGuard) — 本机安全卫士

On-device Android 安全卫士：本机守护 + Shizuku 深度管理，零云端。

*On-device Android security guard — local guard plus deeper control via Shizuku, no cloud.*

- 不把隐私数据传出去，判断都在手机上做
- 借助 Shizuku 拿到更深的系统能力，不用 root
- ⬇️ [下载 APK](https://github.com/ice-wocker/IceGuard/releases/latest)

### ⚫ [KayaGo](https://github.com/ice-wocker/KayaGo) — 开源 Android 围棋

内置**从零手写的蒙特卡洛树搜索（MCTS）AI**：不联网、不加载任何权重文件，装上就能下。

*Open-source Android Go game with a hand-written MCTS AI in pure Java — zero dependencies, play right after install.*

- 零第三方依赖；多路棋盘，多档棋力
- 项目名取自榧木（kaya）——传统日本棋盘的用材
- ⬇️ [下载 APK](https://github.com/ice-wocker/KayaGo/releases/latest) · `GPL-3.0`

### 🎯 [GunFire](https://github.com/ice-wocker/GunFire) — 安卓枪战游戏

纯 Java + **OpenGL ES 2.0 手写渲染**，Unity / Godot / libGDX 一个都没引。

*A tiny Android shooter — zero dependencies, zero permissions, hand-written OpenGL ES rendering with no engine and no assets.*

- **零素材文件**：没贴图、没模型、没音频，世界全是程序生成的几何体
- **零权限**——不是「承诺不上传」，是技术上没有权限可用
- 核心逻辑不依赖 Android API，单测在普通 JVM 上毫秒级跑完
- ⬇️ [下载 APK](https://github.com/ice-wocker/GunFire/releases/latest) · `MIT`

### 🔌 [iceProxy](https://github.com/ice-wocker/iceProxy) — 免费模型的 OpenAI 协议代理

一个 Cloudflare Worker 单文件，把一个入口变成 OpenAI 兼容 API，Cline / Cursor / ChatBox 填上地址就能用。

*A single-file Cloudflare Worker that turns free models into an OpenAI-compatible API, with multi-account rotation and fallback.*

- 覆盖 Qwen / Gemini / GLM / Cerebras / Groq 等多个免费模型与 provider
- 多账号轮换 + 多 provider 兜底，免费额度也能稳定跑

### 📱 [droid-mcp](https://github.com/ice-wocker/droid-mcp) — 手机变 MCP 工具

安卓手机变成 MCP 工具：短信 / 电话 / 剪贴板 / 相机 / 传感器 / 文件，AI 直接动手。

*Your Android phone as MCP tools in one dependency-free file, plus a companion APK.*

- 三后端：Termux、companion APK（不用装 Termux）、mock（没手机也能玩）
- 网页管家 + 官方 Skill + 工具 × 后端兼容矩阵
- ⬇️ [下载 companion APK](https://github.com/ice-wocker/droid-mcp/releases/latest)

### 🎧 [MusicFusion](https://github.com/ice-wocker/MusicFusion) — 聚合音乐播放器

多源聚合 + 全离线缓存，纯 Java 零依赖。

*Aggregated music player for Android — multiple public sources, full offline caching, pure Java, zero dependencies.*

- 来源是 Audius、Internet Archive、RadioBrowser、SomaFM、Openverse、Jamendo 这类合法公开曲库与电台
- 听过的自动缓存，断网也能继续放
- ⬇️ [MusicFusion](https://github.com/ice-wocker/MusicFusion/releases/latest) · [MusicFusionAI](https://github.com/ice-wocker/MusicFusionAI/releases/latest)（端侧 LLM 增强模块）

### 📖 [iceReading](https://github.com/ice-wocker/iceReading) — EPUB 阅读器

纯 Java、单 dex、零依赖的 Android EPUB 阅读器。

*Pure Java Android EPUB reader. Zero dependencies, single dex. Local-only, no cloud sync, no tracking, no ads.*

- OPDS 发现、阅读模式、多套主题；书在本地，不云同步、不追踪、不塞广告
- ⬇️ [下载 APK](https://github.com/ice-wocker/iceReading/releases/latest)

### 💻 两个命令行工具

- [nvidia-engineer-pro](https://github.com/ice-wocker/nvidia-engineer-pro) — 终端 AI 编程助手，单个纯标准库 Python 文件：多工具调用、流式输出、并行读取、shadow-git 检查点
- [mini-code](https://github.com/ice-wocker/mini-code) — 迷你版 Claude Code，Node.js + Ink 写的终端助手，任何 OpenAI 兼容 API 都能接

### 🧪 [spark-distill-1b](https://github.com/ice-wocker/spark-distill-1b) — 把大模型蒸进 1B

把 Muse Spark 的风格蒸进 MiniCPM5-1B，最后转成 GGUF 直接上手机。

*Distilling Muse Spark style into MiniCPM5-1B — free-GPU QLoRA pipeline, exported to GGUF for phones.*

- Unsloth QLoRA，免费卡半小时跑完；另有纯 transformers 兜底脚本
- 评测脚本 + LoRA 合并 + GGUF 导出，直通 Termux 里的 llama.cpp

### 🌐 [icesuite](https://github.com/ice-wocker/icesuite) — 作品集站点 + 应用商店

把这些 App 收进一个纯静态站，一键下齐全部 APK。

*Portfolio site + app store for everything above — pure static, one click to grab all APKs.*

- Python 标准库渲染，零框架零构建链；可 Fork 改成你自己的
- 👉 [ice-wocker.github.io/icesuite](https://ice-wocker.github.io/icesuite/)

## 📦 全部项目

二十多个原创仓库，完整列表见 [Repositories](https://github.com/ice-wocker?tab=repositories)。下面是常用入口：

| 项目 | 一句话 | 技术栈 | 装上试 |
| --- | --- | --- | :-: |
| **[iceScribe](https://github.com/ice-wocker/iceScribe)** | 离线语音转写：内置 whisper.cpp，零 INTERNET 权限，边录边转 | Java | [⬇️](https://github.com/ice-wocker/iceScribe/releases/latest) |
| **[ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser)** | 魔搭模型库：下载 GGUF + 内置 llama.cpp 离线对话，带可调终端/联网的智能体 | Java | [⬇️](https://github.com/ice-wocker/ModelScopeBrowser/releases/latest) |
| **[iceScan](https://github.com/ice-wocker/iceScan)** | 随身扫描仪：自动找边 + 透视拉直 + 去阴影，多页合成 PDF，零权限 | Java | [⬇️](https://github.com/ice-wocker/iceScan/releases/latest) |
| **[iceBrowser](https://github.com/ice-wocker/iceBrowser)** | 纯 Java 浏览器：0 依赖、真多 Tab、多引擎、广告拦截、阅读模式 | Java | [⬇️](https://github.com/ice-wocker/iceBrowser/releases/latest) |
| **[iceReading](https://github.com/ice-wocker/iceReading)** | 纯 Java EPUB 阅读器：0 依赖、OPDS 发现、多主题，零云同步 | Java | [⬇️](https://github.com/ice-wocker/iceReading/releases/latest) |
| **[KayaGo](https://github.com/ice-wocker/KayaGo)** | 开源围棋：从零手写 MCTS AI，零依赖，多路棋盘多档棋力 | Java | [⬇️](https://github.com/ice-wocker/KayaGo/releases/latest) |
| **[GunFire](https://github.com/ice-wocker/GunFire)** | 枪战游戏：OpenGL ES 手写渲染、零素材、零权限，单测在 JVM 上跑 | Java | [⬇️](https://github.com/ice-wocker/GunFire/releases/latest) |
| **[MusicFusion](https://github.com/ice-wocker/MusicFusion)** | 聚合音乐播放器：多源聚合、全离线缓存 | Java | [⬇️](https://github.com/ice-wocker/MusicFusion/releases/latest) |
| **[MusicFusionAI](https://github.com/ice-wocker/MusicFusionAI)** | MusicFusion 的 AI 模块：端侧 LLM + 歌词翻译 + Android Auto / Wear OS | Java | [⬇️](https://github.com/ice-wocker/MusicFusionAI/releases/latest) |
| **[IceGuard](https://github.com/ice-wocker/IceGuard)** | 本机安全卫士：本机守护 + Shizuku 深度管理，零云端 | Kotlin | [⬇️](https://github.com/ice-wocker/IceGuard/releases/latest) |
| **[droid-mcp](https://github.com/ice-wocker/droid-mcp)** | 手机变 MCP 工具：三后端，单文件零依赖 + companion APK | Python | [⬇️](https://github.com/ice-wocker/droid-mcp/releases/latest) |
| **[iceLLM](https://github.com/ice-wocker/iceLLM)** | 一行命令把安卓机变成 OpenAI 兼容的本地 AI 服务器 | Shell | 命令 |
| **[iceProxy](https://github.com/ice-wocker/iceProxy)** | 免费模型的 OpenAI 协议代理（Cloudflare Workers，多账号轮换 + 兜底） | JavaScript | 部署 |
| **[xstech-terminal](https://github.com/ice-wocker/xstech-terminal)** | 把网页端能力包成 OpenAI 兼容端点，改个 `base_url` 就能用 | Python | — |
| **[nvidia-engineer-pro](https://github.com/ice-wocker/nvidia-engineer-pro)** | 终端 AI 编程助手：单文件纯标准库 Python，多工具 + shadow-git | Python | — |
| **[mini-code](https://github.com/ice-wocker/mini-code)** | 迷你版 Claude Code：Node.js + Ink，接任何 OpenAI 兼容 API | JavaScript | — |
| **[spark-distill-1b](https://github.com/ice-wocker/spark-distill-1b)** | 大模型蒸进 1B：免费卡 QLoRA 管线，转 GGUF 上手机 | Python | — |
| **[frontier-knowledge-base](https://github.com/ice-wocker/frontier-knowledge-base)** | 前沿科技知识库：多领域专题文档，事实性内容逐条附来源链接 | Markdown | — |
| **[icesuite](https://github.com/ice-wocker/icesuite)** | 作品集站点 + 应用商店：纯静态，一键下齐全部 APK | Python | [🌐](https://ice-wocker.github.io/icesuite/) |

## 🧭 我在意的几件事

- **体积**：浏览器、阅读器、围棋、3D 游戏都按「几百 KB」这个量级做——具体数字随版本变动，以各仓库 Release 里的实际包为准
- **依赖**：能自己写就不引库。少一个依赖，少一次供应链风险
- **离线优先**：模型推理、看书、下棋、听歌、扫描都不依赖云端；不强制登录，不追踪，不塞广告
- **权限克制**：用不到的权限一个都不要——扫描 App 的权限列表可以是空的，录音笔只要一个麦克风
- **出处可查**：连知识库都要求逐条标注来源，宁可并列呈现分歧，也不给单一结论
- **真免费**：不拿 API Key 当门槛，能用免费额度轮换的就轮换

> 每个项目 README 里的体积/依赖数都以**实际构建出的包**为准，不是估算值。
> 体积声明与实际不符的会当场改掉。

## 🤝 找到我

- GitHub：[@ice-wocker](https://github.com/ice-wocker)
- 想联系我：欢迎去任意仓库提 Issue 或到 Discussions 留言，看到会回。

欢迎 Issue、PR、Star、Fork。哪个轮子你用得上，点个 Star 就是最大的鼓励 ⭐

<sub>本主页只放不会过期的东西；每个项目的体积、依赖数、能力以各自 README 与 Release 为准。</sub>
