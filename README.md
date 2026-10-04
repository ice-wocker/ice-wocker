<div align="center">

<img src="https://github.com/ice-wocker.png" width="116" alt="ice-wocker" />

# 嗨，我是冰块制造机 🧊

**零依赖 · 单文件 · 极小体积 · 把 AI 塞进手机**

*Tiny, dependency-free Android tools and on-device AI — offline first.*

[![关注](https://img.shields.io/github/followers/ice-wocker?label=%E5%85%B3%E6%B3%A8&color=FF5A2D&style=flat)](https://github.com/ice-wocker?tab=followers)
[![Java](https://img.shields.io/badge/Java-Android%20%E4%B8%BB%E5%8A%9B-007396?logo=openjdk&logoColor=white)](#-全部项目)
[![关键词](https://img.shields.io/badge/%E5%85%B3%E9%94%AE%E8%AF%8D-%E9%9B%B6%E4%BE%9D%E8%B5%96%20%C2%B7%20%E7%A6%BB%E7%BA%BF%20%C2%B7%20%E6%9E%81%E5%B0%8F%E4%BD%93%E7%A7%AF-8B5CF6)](#-我在意的几件事)
[![License](https://img.shields.io/badge/License-MIT%20%2F%20GPL--3.0-3DA639)](https://github.com/ice-wocker?tab=repositories)

[![My Skills](https://skillicons.dev/icons?i=java,python,js,nodejs,shell,androidstudio,gradle)](https://skillicons.dev)

![stats](https://github-readme-stats.vercel.app/api?username=ice-wocker&show_icons=true&theme=transparent)
![langs](https://github-readme-stats.vercel.app/api/top-langs/?username=ice-wocker&layout=compact&theme=transparent)

![visitors](https://visitor-badge.laobi.icu/badge?page_id=ice-wocker.ice-wocker)

</div>

---

我造一些**零依赖、单文件、真免费**的小轮子，也顺手把大模型塞进手机里跑。

主力写 Android（纯 Java、单 dex、能不引依赖就不引），需要的时候也写 Cloudflare Workers（JavaScript）和 Shell。判断一个项目做得行不行，我习惯先看三件事：**安装包多大、有几个第三方依赖、断网还能不能用**。

这个账号下所有项目均为原创。

## 🛠️ 代表作

### 🎙️ [iceScribe](https://github.com/ice-wocker/iceScribe) — 把手机变成一支离线录音笔

中文：离线语音转写的 Android App，内置 whisper.cpp，全程本机推理，不申请 INTERNET 权限。

*English: Offline voice-transcription Android app with built-in whisper.cpp — inference stays on-device, no INTERNET permission.*

- 内置 **whisper.cpp**，录音结束自动转写；**不申请 INTERNET 权限**，录音和文字没有任何路径离开这台设备
- 纯 CPU 离线推理：边录边重采样成 16 kHz 单声道落盘，转写按段流式读取，**录一小时内存也不涨**
- 支持导入已有音频（m4a / mp3 / wav / ogg）、中/英/自动检测与翻译、历史记录、模型导入管理
- 零第三方依赖；APK 内含基础模型，**装完即用**，不用自己下模型

### 🧠 [ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser) — 魔搭模型库

中文：魔搭模型库轻量 Android 客户端，分页浏览与搜索大模型，内置 llama.cpp 离线对话与能调用终端和联网的智能体。

*English: A lightweight ModelScope client for Android — browse and search models, download GGUF, and chat offline via built-in llama.cpp with an agent that can run shell commands and search the web.*

- 浏览魔搭大模型（分页 / 搜索 / 排序 / 多维筛选），应用内下载 `.gguf`（断点续传 + 完整性校验）
- 内置 **llama.cpp**，**纯 CPU 离线推理**；arm64 编了多档指令集后端，运行时按芯片自动选档
- 对话页是个**能动手的智能体**：模型可自主调用手机终端、联网搜索、读写工作区文件、预览网页
- 默认上下文 8192 / 单次输出 4096 tokens，KV 量化 + 前缀复用

### 🌐 [iceBrowser](https://github.com/ice-wocker/iceBrowser) — Android 浏览器

中文：纯 Java 编写的 Android 浏览器，零依赖、单 dex，带多标签、广告拦截与阅读模式。

*English: A pure-Java Android browser — zero dependencies, single dex, with true multi-tab, ad blocking and reader mode.*

- 纯 Java / 单 dex / **0 第三方依赖**（以仓库 README 为准）
- 真正的多 Tab，多个搜索引擎可切换，内置广告拦截 / 阅读模式 / 无痕模式
- `MIT`

### 📱 [iceLLM](https://github.com/ice-wocker/iceLLM) — 一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器

中文：一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器，局域网内可用，完全离线。

*English: Turn your Android phone into an OpenAI-compatible local AI server with one command — available on your LAN, fully offline.*

```bash
curl -fsSL https://raw.githubusercontent.com/ice-wocker/iceLLM/main/ice-llm.sh | bash
```

- 跑在 Android (Termux) 上，装完就在局域网里得到一个本地大模型
- 自带 WebUI，同时暴露 `http://<手机IP>:8080/v1/chat/completions`——任何 OpenAI 客户端改个 `base_url` 就能用
- 支持 MiniCPM5 / Qwen2.5 / Qwen3；**完全离线**：不要 API Key、不上云、数据不出设备
- `MIT`

### 📄 [iceScan](https://github.com/ice-wocker/iceScan) — 随身扫描仪

中文：离线文档扫描，拍一张自动找边、透视拉直、去阴影，多页合成 PDF，零权限零依赖不联网。

*English: Offline document scanner — snap a page to auto-detect edges, flatten and export multi-page PDFs, with zero permissions and zero dependencies.*

- 拍一张，自动找出纸张四边、透视拉直、去阴影，多页合成一个 PDF
- **权限列表是空的**：拍照走系统相机、选图走系统文件选择器、导出用自带 `ContentProvider`，三件事都不要权限
- 手写单应矩阵求解 + 双线性反查采样；黑白档用 Bradley 自适应阈值（积分图，O(像素数)），阴影区不会被整片染黑
- 零第三方依赖、零权限、不联网

### ⚫ [KayaGo](https://github.com/ice-wocker/KayaGo) — 开源 Android 围棋

中文：开源 Android 围棋 App，内置从零手写的 MCTS AI，纯 Java 零依赖，装上就能下。

*English: Open-source Android Go game with a hand-written MCTS AI in pure Java — zero dependencies, play right after install.*

- 内置**从零手写的蒙特卡洛树搜索（MCTS）AI**：不联网、不加载任何权重文件，装上就能下
- 零第三方依赖；多路棋盘，多档棋力
- 项目名取自榧木（kaya）——传统日本棋盘的用材
- `GPL-3.0`

### 🎯 [GunFire](https://github.com/ice-wocker/GunFire) — 安卓枪战游戏

中文：纯粹的安卓枪战游戏，零第三方依赖零权限，OpenGL ES 手写渲染，无引擎无素材。

*English: A tiny Android shooter — zero dependencies, zero permissions, hand-written OpenGL ES rendering with no engine and no assets.*

- 纯 Java + **OpenGL ES 2.0 手写渲染**，Unity / Godot / libGDX 一个都没引
- **零素材文件**：没贴图、没模型、没音频，世界全是程序生成的几何体
- **零权限**——不是「承诺不上传」，是技术上没有权限可用
- 核心逻辑不依赖 Android API，单测在普通 JVM 上毫秒级跑完
- `MIT` · [⬇️ 直接下载 APK](https://github.com/ice-wocker/GunFire/releases/latest/download/app-release.apk)

### 🔌 [iceProxy](https://github.com/ice-wocker/iceProxy) — 免费模型的 OpenAI 协议代理

中文：把免费模型变成 OpenAI 兼容 API 的 Cloudflare Worker 单文件代理，支持多账号轮换与多源兜底。

*English: A single-file Cloudflare Worker that turns free models into an OpenAI-compatible API, with multi-account rotation and fallback.*

- 一个 Cloudflare Worker 单文件，把一个入口变成 OpenAI 兼容 API，Cline / Cursor / ChatBox 填上地址就能用
- 覆盖 Qwen / Gemini / GLM 等多个免费模型与多个 provider
- 多账号轮换 + 多 provider 兜底，免费额度也能稳定跑

## 📦 全部项目

十多个原创项目，完整列表见 [Repositories](https://github.com/ice-wocker?tab=repositories)。下面是常用入口：

| 项目 | 一句话 | 技术栈 |
| --- | --- | --- |
| **[iceScan](https://github.com/ice-wocker/iceScan)** | 随身扫描仪：自动找边 + 透视拉直 + 去阴影，多页合成 PDF，零权限零依赖不联网 | Java |
| **[iceScribe](https://github.com/ice-wocker/iceScribe)** | 离线语音转写：内置 whisper.cpp，零 INTERNET 权限，边录边转、常数级内存 | Java |
| **[ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser)** | 魔搭模型库：浏览大模型 + 下载 GGUF + 内置 llama.cpp 离线对话，带能调用终端/联网的智能体 | Java |
| **[iceLLM](https://github.com/ice-wocker/iceLLM)** | 一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器（WebUI + API，完全离线） | Shell |
| **[iceProxy](https://github.com/ice-wocker/iceProxy)** | 免费模型的 OpenAI 协议代理（Cloudflare Workers，多账号轮换 + 兜底） | JavaScript |
| **[iceBrowser](https://github.com/ice-wocker/iceBrowser)** | 纯 Java 浏览器：0 依赖、真多 Tab、多引擎、广告拦截、阅读模式 | Java |
| **[iceReading](https://github.com/ice-wocker/iceReading)** | 纯 Java EPUB 阅读器：0 依赖、OPDS 发现、多主题，零云同步 / 追踪 / 广告 | Java |
| **[KayaGo](https://github.com/ice-wocker/KayaGo)** | 开源 Android 围棋：从零手写 MCTS AI，零依赖，多路棋盘多档棋力 | Java |
| **[GunFire](https://github.com/ice-wocker/GunFire)** | 安卓枪战游戏：OpenGL ES 手写渲染、零素材、零权限，单测在 JVM 上跑 | Java |
| **[MusicFusion](https://github.com/ice-wocker/MusicFusion)** | 聚合音乐播放器：多源聚合、全离线缓存 | Java |
| **[MusicFusionAI](https://github.com/ice-wocker/MusicFusionAI)** | MusicFusion 的 AI 增强模块：端侧 LLM + AI 任务 + 歌词翻译 + Android Auto / Wear OS | Java |
| **[frontier-knowledge-base](https://github.com/ice-wocker/frontier-knowledge-base)** | 前沿科技知识库：多领域专题文档，事实性内容逐条附来源链接 | Markdown |
| **[ice-wocker](https://github.com/ice-wocker/ice-wocker)** | 就是你现在看的这个仓库——个人主页 | — |

## 🧭 我在意的几件事

- **体积**：浏览器、阅读器、围棋、3D 游戏都追求极小体积，具体数字以各仓库 README 的实际构建包为准
- **依赖**：能自己写就不引库。少一个依赖，少一次供应链风险
- **离线优先**：模型推理、看书、下棋、听歌、扫描都不依赖云端；不强制登录，不追踪，不塞广告
- **权限克制**：用不到的权限一个都不要——扫描 App 和录音笔的权限列表可以做到"空"或"只有一个麦克风"
- **出处可查**：连知识库都要求逐条标注来源，宁可并列呈现分歧，也不给单一结论
- **真免费**：不拿 API Key 当门槛，能用免费额度轮换的就轮换

> 每个项目 README 里的体积/依赖数都以**实际构建出的包**为准，
> 不是估算值。体积声明与实际不符的会当场改掉。

## 🤝 找到我

- GitHub：[@ice-wocker](https://github.com/ice-wocker)
- 想联系我：欢迎去任意仓库提 Issue，或到 Discussions 里留言，看到会回。

欢迎 Issue、PR、Star、Fork。哪个轮子你用得上，点个 Star 就是最大的鼓励 ⭐

<sub>本主页只放不会过期的东西；每个项目的体积、依赖数、能力以各自 README 为准。</sub>
