<div align="center">

<img src="https://github.com/ice-wocker.png" width="116" alt="ice-wocker" />

# 嗨，我是冰块制造机 🧊

**零依赖 · 单文件 · 极小体积 · 把 AI 塞进手机**

[![关注](https://img.shields.io/github/followers/ice-wocker?label=%E5%85%B3%E6%B3%A8&color=FF5A2D)](https://github.com/ice-wocker?tab=followers)
[![开源项目](https://img.shields.io/badge/%E5%BC%80%E6%BA%90%E9%A1%B9%E7%9B%AE-11-4B5563)](#-全部项目)
[![Java](https://img.shields.io/badge/Java-7%20%E4%B8%AA%E9%A1%B9%E7%9B%AE-007396?logo=openjdk&logoColor=white)](#-全部项目)
[![关键词](https://img.shields.io/badge/%E5%85%B3%E9%94%AE%E8%AF%8D-%E9%9B%B6%E4%BE%9D%E8%B5%96%20%C2%B7%20%E7%A6%BB%E7%BA%BF%20%C2%B7%20%E6%9E%81%E5%B0%8F%E4%BD%93%E7%A7%AF-8B5CF6)](#-我在意的几件事)
[![License](https://img.shields.io/badge/License-MIT%20%2F%20GPL--3.0-3DA639)](https://github.com/ice-wocker?tab=repositories)

</div>

---

我造一些**零依赖、单文件、真免费**的小轮子，也顺手把大模型塞进手机里跑。

主力写 Android（纯 Java、单 dex、能不引依赖就不引），需要的时候也写 Cloudflare Workers（JavaScript）和 Shell。判断一个项目做得行不行，我习惯先看三件事：**安装包多大、有几个第三方依赖、断网还能不能用**。

这个账号 2026 年 8 月底开的，一个月里攒下 11 个原创项目，一个 fork 都没有。

## 🛠️ 代表作

### 🎙️ [iceScribe](https://github.com/ice-wocker/iceScribe) — 把手机变成一支离线录音笔

- 内置 **whisper.cpp v1.9.4**，录音结束自动转写；**不申请 INTERNET 权限**，录音和文字没有任何路径离开这台设备
- 纯 CPU 离线推理：边录边重采样成 16 kHz 单声道落盘，转写按段流式读取，**录一小时内存也不涨**
- 支持导入已有音频（m4a / mp3 / wav / ogg）、中/英/自动检测与翻译、历史记录、模型导入管理
- 零第三方依赖；APK 约 **59 MB**（内含 57 MB 的 base 模型，**装完即用**，不用自己下模型）

### 🌐 [iceBrowser](https://github.com/ice-wocker/iceBrowser) — Android 浏览器

- 纯 Java / 单 dex / **0 第三方依赖**，APK **81 KB**（同类普遍 30 MB 以上）
- 真正的多 Tab，4 个搜索引擎可切换，内置广告拦截 / 阅读模式 / 无痕模式
- `MIT`

### 📱 [iceLLM](https://github.com/ice-wocker/iceLLM) — 一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器

```bash
curl -fsSL https://raw.githubusercontent.com/ice-wocker/iceLLM/main/ice-llm.sh | bash
```

- 跑在 Android (Termux) 上，装完就在局域网里得到一个本地大模型
- 自带 WebUI，同时暴露 `http://<手机IP>:8080/v1/chat/completions`——任何 OpenAI 客户端改个 `base_url` 就能用
- 支持 MiniCPM5 / Qwen2.5 / Qwen3；**完全离线**：不要 API Key、不上云、数据不出设备
- `MIT`

### 🧠 [ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser) — 魔搭模型库

- 浏览魔搭全部大模型（分页 / 搜索 / 排序 / 六维筛选），应用内下载 `.gguf`（断点续传 + 完整性校验）
- 内置 **llama.cpp**，**纯 CPU 离线推理**；arm64 编了多档指令集后端，运行时按芯片自动选档，i8mm / SVE 机型走更快的 int8 矩阵乘
- 对话页是个**能动手的智能体**：模型可自主调用手机终端、联网搜索、读写工作区文件、预览网页
- 默认上下文 8192 / 单次输出 4096 tokens，KV 量化 + 前缀复用

### 🔌 [iceProxy](https://github.com/ice-wocker/iceProxy) — 免费模型的 OpenAI 协议代理

- 一个 Cloudflare Worker 单文件，把一个入口变成 OpenAI 兼容 API，Cline / Cursor / ChatBox 填上地址就能用
- 覆盖 Qwen3-Max · GLM-5.3 · DeepSeek-V4 · GPT-OSS-120B · Llama-4 · Kimi-K3
- 多账号轮换 + 多 provider 兜底，免费额度也能稳定跑

### ⚫ [KayaGo](https://github.com/ice-wocker/KayaGo) — 开源 Android 围棋

- 内置**从零手写的蒙特卡洛树搜索（MCTS）AI**：不联网、不加载任何权重文件，装上就能下
- 零第三方依赖，APK **约 70 KB**；9 / 13 / 19 路棋盘，5 档棋力（约 0.6 秒 ~ 17 秒每手）
- 项目名取自榧木（kaya）——传统日本棋盘的用材
- `GPL-3.0`

## 📦 全部项目

| 项目 | 一句话 | 技术栈 |
| --- | --- | --- |
| **[iceScribe](https://github.com/ice-wocker/iceScribe)** | 离线语音转写：内置 whisper.cpp + base 模型开箱即用，零 INTERNET 权限，边录边转、常数级内存 | Java |
| **[ModelScopeBrowser](https://github.com/ice-wocker/ModelScopeBrowser)** | 魔搭模型库：浏览全部大模型 + 下载 GGUF + 内置 llama.cpp 离线对话，带能调用终端/联网的智能体 | Java |
| **[iceLLM](https://github.com/ice-wocker/iceLLM)** | 一行命令把安卓手机变成 OpenAI 兼容的本地 AI 服务器（WebUI + API，完全离线） | Shell |
| **[iceProxy](https://github.com/ice-wocker/iceProxy)** | 免费模型的 OpenAI 协议代理（Cloudflare Workers，多账号轮换 + 多 provider 兜底） | JavaScript |
| **[iceBrowser](https://github.com/ice-wocker/iceBrowser)** | 纯 Java 浏览器：0 依赖、81 KB APK、真多 Tab、4 引擎、广告拦截、阅读模式 | Java |
| **[iceReading](https://github.com/ice-wocker/iceReading)** | 纯 Java EPUB 阅读器：0 依赖、不到 100 KB、OPDS 发现、4 主题，零云同步 / 追踪 / 广告 | Java |
| **[KayaGo](https://github.com/ice-wocker/KayaGo)** | 开源 Android 围棋：从零手写 MCTS AI，零依赖、约 70 KB，9/13/19 路 5 档棋力 | Java |
| **[MusicFusion](https://github.com/ice-wocker/MusicFusion)** | 聚合音乐播放器：900 万+ 合法曲目 + 2945 个电台，四源聚合、全离线缓存 | Java |
| **[MusicFusionAI](https://github.com/ice-wocker/MusicFusionAI)** | MusicFusion v14 的 AI 增强模块：端侧 LLM + 5 大 AI 任务 + 卡拉OK + Android Auto / Wear OS | Java |
| **[frontier-knowledge-base](https://github.com/ice-wocker/frontier-knowledge-base)** | 前沿科技知识库：九大领域 163 篇专题文档，事实性内容逐条附来源链接 | Markdown |
| **[ice-wocker](https://github.com/ice-wocker/ice-wocker)** | 就是你现在看的这个仓库——个人主页 | — |

## 🧭 我在意的几件事

- **体积**：81 KB 的浏览器、不到 100 KB 的阅读器、约 70 KB 的围棋 AI。塞得进手机，也塞得进缓存
- **依赖**：能自己写就不引库。少一个依赖，少一次供应链风险，也少几十 MB
- **离线优先**：模型推理、看书、下棋、听歌都不依赖云端；不强制登录，不追踪，不塞广告
- **出处可查**：连知识库都要求逐条标注来源，宁可并列呈现分歧，也不给单一结论
- **真免费**：不拿 API Key 当门槛，能用免费额度轮换的就轮换

## 📊 数据

| 项 | 值 |
| --- | --- |
| 公开仓库 | **11** 个，全部原创（0 fork） |
| 语言 | Java ×7 · JavaScript ×1 · Shell ×1 · 纯文档 ×2 |
| 协议 | MIT ×4 · GPL-3.0 ×1 · 其余未标注 |
| 最小安装包 | **81 KB**（iceBrowser） |

## 🤝 找到我

- GitHub：[@ice-wocker](https://github.com/ice-wocker)
- 邮箱：ice@users.noreply.github.com

欢迎 Issue、PR、Star、Fork。哪个轮子你用得上，点个 Star 就是最大的鼓励 ⭐

<sub>最后更新：2026-09-27</sub>