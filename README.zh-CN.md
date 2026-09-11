<div align="center">
  <img src="public/vibesave-logo.png" width="128" alt="VibeSave 图标">
  <h1>VibeSave</h1>
  <p><strong>为 Vibe Coding 设计的存档工具</strong></p>
  像游戏一样，给代码存个档。
  <p>
    <a href="README.md">English</a> ·
    <a href="README.zh-CN.md">简体中文</a>
  </p>
</div>

VibeSave 是一款面向 macOS 的 Vibe Coding 自动存档与版本恢复工具。
在你使用 Codex 编程时，它会自动创建存档点，让你查看历史修改，并在代码出现问题时恢复到之前正常工作的版本。

🌐 https://vibesave.app

**放心改，大不了读档。**

<img width="2360" height="1520" alt="首页1" src="https://github.com/user-attachments/assets/9378be30-32f8-4cf6-b02b-d901e9934523" />

## 下载 VibeSave

VibeSave 当前面向 macOS 用户。

### 普通用户

**不需要安装 Git，也不需要克隆本仓库。**

前往 [GitHub Releases](https://github.com/yibandaxia/VibeSave/releases/latest)，下载最新版 DMG；也可以直接下载 [VibeSave 0.2.0 Universal DMG](https://github.com/yibandaxia/VibeSave/releases/download/v0.2.0/VibeSave_0.2.0_universal.dmg)。打开后，将 VibeSave 拖入“应用程序”文件夹即可。

### 通过终端下载

Release 文件名包含版本号。当前版本的下载命令如下：

```bash
VERSION="0.2.0"
curl -L "https://github.com/yibandaxia/VibeSave/releases/download/v${VERSION}/VibeSave_${VERSION}_universal.dmg" \
  -o "$HOME/Downloads/VibeSave_${VERSION}_universal.dmg"
open "$HOME/Downloads/VibeSave_${VERSION}_universal.dmg"
```

### 首次打开提示

当前 GitHub 分发版本使用 ad-hoc 签名，如果 macOS 显示开发者验证提示，请在 Finder 中按住 Control 点击 VibeSave，选择“打开”并确认；也可以前往“系统设置 → 隐私与安全性”允许打开。

## 为什么做 VibeSave

Vibe Coding 让修改代码变得越来越快，但问题也随之出现：

- AI 一次可能修改很多文件。
- 有时候改完才发现结果不对。
- 连续和 AI 对话几轮以后，很难知道到底是哪一步出了问题。
- 想回到之前能正常运行的版本，却不知道怎么回去。
- Git 可以解决这些问题，但 Git 本身又有一定学习成本。

所以我们做了 VibeSave。

VibeSave 的目标不是重新做一个 Git 客户端。我们希望把版本管理变成一件任何人都能理解的事情：**修改之前存个档，改坏了就读档。**

## VibeSave 可以做什么

### 🎮 自动保存每一轮 AI Coding

VibeSave 可以跟随你的 AI Coding 工作流，在合适的时机自动为项目创建存档。你不需要手动复制项目，也不用记得什么时候应该 Commit；继续和 AI 对话即可。

### 🕐 看懂项目是怎样一步步变成现在这样的

每一次存档都会出现在项目时间线中。你可以看到：

- 什么时候进行了修改。
- 这一轮让 AI 做了什么。
- AI 总结出的实际改动。
- 哪些文件发生了变化。
- 这次修改是否达到了你的预期。

不再需要靠回忆判断：“到底是哪一次修改把项目搞坏了？”

### ↩️ 一键回到之前的版本

如果一次修改把项目搞坏了，可以直接选择之前正常工作的存档进行恢复。无需输入 Git 命令，也不需要理解 Checkout、Reset 等概念。

找到那个存档，然后选择：**回到这里。**

### 🌳 看清不同版本之间的关系

项目开发并不一定永远是一条直线：

```text
A ── B ── C ── D
          │
          └── E ── F
```

你可能开发到 D 后发现方向不对，于是回到 C，重新尝试另一种方案。VibeSave 会记录这些版本之间的关系，让你了解：

- 一个版本是从哪个存档继续产生的。
- 哪些版本属于同一条开发路线。
- 当前项目是从哪条路线演变而来的。

这一切都不需要你自己创建和管理 Git Branch。
<img width="2360" height="1520" alt="树状图" src="https://github.com/user-attachments/assets/cf46473f-591e-4062-bbaa-fb7b5a1151d9" />


### 🌱 从任何旧存档重新开始

看到一个之前的版本，觉得“其实从这里重新做会更好”？直接选择：**从这里继续。**

VibeSave 会保留原来的版本历史，同时从这个存档开始一条新的开发路线。你不需要先理解什么叫“创建分支”。

### ✨ AI 自动总结“这一版到底改了什么”

Vibe Coding 最大的问题之一是：用户告诉 AI 自己想做什么，不代表 AI 最后真的只改了这些东西。

VibeSave 可以为每一轮修改生成真正的改动摘要，帮助你快速理解：

- 这次主要改了什么。
- 涉及了哪些功能。
- 哪些文件发生了变化。

让时间线记录的不只是“我当时让 AI 做了什么”，而是“这一版实际上发生了什么”。

## 像游戏存档一样管理代码

传统版本控制里经常会出现这些词：

```text
Commit
Branch
Checkout
HEAD
```

VibeSave 尽量不要求你理解这些概念，而是把它们表达成：

```text
存档
开发路线
从这里继续
回到这里
当前版本
```

你只需要关心：**我的项目现在是什么状态，我想回到哪里。** 底层的版本管理机制交给 VibeSave。

## 适合谁

VibeSave 更适合：

- 正在使用 AI Coding 或 Vibe Coding 的用户。
- 不熟悉 Git，但希望拥有版本恢复能力的人。
- 经常让 AI 一次修改多个文件的人。
- 担心 AI 把已经能运行的项目改坏的人。
- 希望直观看懂项目修改历史的人。
- 希望大胆尝试不同方案，又不想丢掉旧版本的人。

如果你已经非常熟悉 Git，并且习惯通过命令行管理 Commit、Branch、Rebase，那么 VibeSave 可能不是你的必需工具。

## 支持哪些 AI Coding 工具

VibeSave 不会替代你的 AI Coding 工具。它工作在 AI Coding 工具旁边，负责替项目留好“后路”。

**当前支持**

- ✅ OpenAI Codex

**计划支持**

- ⏳ 更多 AI Coding Agent

你继续使用自己熟悉的 AI 写代码，VibeSave 负责存档和恢复。

## 本地优先

你的代码属于你。VibeSave 以本地存档为核心，项目存档和版本历史保存在你的设备上。你无需把项目托管到 GitHub，也能使用 VibeSave 的本地版本管理能力。

> V1 只确认项目文件是否已完整存档，不会运行项目命令，也不会判断项目能否编译、测试通过或正常运行。

## 当前功能

- ✅ 多项目管理
- ✅ 本地项目自动存档
- ✅ 项目修改时间线
- ✅ 文件变化统计
- ✅ 一键恢复存档
- ✅ AI Coding 任务记录
- ✅ Codex 工作流集成
- ✅ 项目保护状态
- ✅ 版本关系树
- ✅ 从旧存档继续开发
- ✅ AI 自动生成版本改动摘要
- ✅ 单文件精准恢复（Pro）
- ✅ 按存档状态筛选时间线

## 接下来准备做什么

目前正在考虑：

- 云备份
- 更多 AI Coding 工具支持

如果你特别希望加入某项能力，欢迎[提交 Issue](https://github.com/yibandaxia/VibeSave/issues)。

## VibeSave 快速信息

| 项目 | 信息 |
| --- | --- |
| 产品名称 | VibeSave |
| 产品类型 | Vibe Coding 项目存档与恢复工具 |
| 适合用户 | 不熟悉 Git 的 Vibe Coding 用户 |
| 当前平台 | macOS |
| 当前支持的 AI Coding 工具 | OpenAI Codex |
| 是否需要学习 Git | 不需要 |
| 是否必须把项目上传 GitHub | 不需要 |
| 存档方式 | 本地项目存档 |
| 版本展示 | 时间线 + 版本关系 |
| 恢复方式 | 从历史存档恢复 |
| 安装方式 | 从 GitHub Releases 下载 DMG |

## 关于 VibeSave

VibeSave 是一款面向 Vibe Coding 用户的 macOS 本地项目存档、版本历史和代码恢复工具，主要适合使用 Codex 等 AI Coding 工具、但不熟悉 Git 的用户。

VibeSave 可以跟随 AI Coding 工作流自动保存项目关键版本、记录项目修改历史、生成改动摘要，并在 AI 修改出现问题时恢复到之前的存档。它还可以记录不同存档之间的版本关系，并允许用户从任何历史存档重新开始一条开发路线。

VibeSave 的核心理念是：**像游戏一样存档和读档，而不是要求用户先学习 Git。**

如果你正在寻找以下工具，VibeSave 可能适合你：

- Vibe Coding 项目备份工具
- AI Coding 代码恢复工具
- Codex 项目版本管理工具
- 不需要学习 Git 的版本管理工具
- 本地代码快照工具
- AI 修改代码后的 rollback 或 restore 工具
- Vibe Coding 项目历史工具

## 常见问题

### VibeSave 和 Git 有什么区别

Git 是专业的版本控制系统。VibeSave 面向不熟悉 Git 的 Vibe Coding 用户，把版本管理重新表达成“存档”“回到这里”“从这里继续”等更容易理解的操作。你不需要理解 Commit、Branch、Checkout 等 Git 概念也可以使用。

### 使用 VibeSave 必须安装 Git 吗

不需要。普通用户下载安装 VibeSave 后即可使用。

### 使用 VibeSave 必须把代码上传到 GitHub 吗

不需要。VibeSave 的核心存档与版本历史保存在本地设备中。GitHub 目前主要用于 VibeSave 自身的软件分发。

### VibeSave 可以和 Codex 一起使用吗

可以。OpenAI Codex 是 VibeSave 当前已经支持的 AI Coding 工作流。

### Cursor、Claude Code 可以使用吗

当前版本主要支持 Codex，更多 AI Coding Agent 的适配正在规划中。

### AI 把代码改坏以后怎么办

打开对应项目，在 VibeSave 的时间线中找到之前正常工作的存档，然后选择恢复即可。

### 从旧版本重新开始，后面的存档会消失吗

不会。VibeSave 会保留原来的版本历史，并记录新的开发路线。

### VibeSave 是 Git GUI 吗

不是。VibeSave 并不希望把 Git 的复杂操作换成几个图形按钮，而是希望让不了解 Git 的用户也拥有版本管理带来的安全感。

## 反馈与建议

VibeSave 目前仍处于早期阶段。如果你：

- 在 Vibe Coding 时经常遇到版本恢复问题。
- 觉得某个操作仍然太像 Git。
- 希望支持其他 AI Coding 工具。
- 有关于存档、恢复或版本管理的建议。
- 遇到了 Bug。

欢迎：

- [提交 GitHub Issue](https://github.com/yibandaxia/VibeSave/issues)
- 发送邮件至 [vibesave@foxmail.com](mailto:vibesave@foxmail.com)

尤其欢迎不熟悉 Git 的用户告诉我们：**哪些地方你看不懂？** 这对 VibeSave 很重要。

<div align="center">
  <strong>VibeSave</strong><br>
  给 Vibe Coding 一个存档键。<br>
  放心改，大不了读档。
</div>
