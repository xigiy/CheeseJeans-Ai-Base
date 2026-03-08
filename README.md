# 🧀 CheeseJeans-Ai-Base (芝士裤)

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-Test-green.svg)](https://github.com/xigiy/CheeseJeans-Ai-Base)
![GitHub last commit](https://img.shields.io/github/last-commit/xigiy/CheeseJeans-Ai-Base)
![GitHub stars](https://img.shields.io/github/stars/xigiy/CheeseJeans-Ai-Base?style=social)
![GitHub forks](https://img.shields.io/github/forks/xigiy/CheeseJeans-Ai-Base?style=social)
![Chrome Web Store](https://img.shields.io/badge/Chrome-支持本地-brightgreen)
![Edge Add-ons](https://img.shields.io/badge/Edge-支持本地-blue)
![Firefox](https://img.shields.io/badge/Firefox-支持本地-orange)

> "你说得对，但是「CheeseJeans-Ai-Base」是由B站UP主FL-xigiy基于OpenAI兼容API开发的智能知识管理插件。插件运行在浏览器扩展环境中，在这里，你浏览的每一篇网页都可以被一键保存，AI会自动为你生成摘要和标签。你将扮演一位名为「芝士裤」的知识收藏家，在浏览中积累智慧，打造属于自己的第二大脑，同时逐步发掘「AI自动化」的乐趣。"

> ✨ 版本说明：CheeseJeans-Ai-Base 是一个运行在 Chrome/Edge/Firefox 上的浏览器插件，基于 OpenAI 兼容 API，支持一键保存网页、AI自动生成摘要、智能标签、全文搜索等功能。你可以把它装在任何浏览器上，让它成为你的私人知识助手。

---

## 📌 版本信息

| 项目 | 信息 |
|------|------|
| 📅 最后更新 | 2026年3月 |
| 📦 当前版本 | 测试中 |
| 🌐 支持浏览器 | Chrome / Edge / Firefox / Kiwi(安卓) |
| 📄 许可证 | MIT |

---

## 📦 功能特点

- 🧀 **一键保存**：点击插件图标，自动获取当前网页标题和URL
- 🤖 **AI摘要**：保存时自动调用AI生成一句话摘要
- 🏷️ **智能标签**：AI自动提取3-5个关键词作为标签
- 📝 **手动笔记**：可添加个人想法和备注
- 🔍 **全文搜索**：搜索标题、摘要、标签中的内容
- 📚 **本地存储**：所有数据存在浏览器IndexedDB，隐私安全
- 🌐 **跨浏览器**：支持 Chrome/Edge/Firefox 及安卓浏览器
- ⚙️ **自定义API**：支持任何OpenAI兼容的API服务商

---

## 🚀 快速开始

### 前置要求

1. 一个支持 OpenAI 兼容格式的 API Key（如 OpenAI、MistralAI、DeepSeek 等）
2. Chrome / Edge / Firefox 浏览器

### 安装步骤

#### 方法一：从源码安装（开发模式）

1. 下载本仓库到本地
```bash
   git clone https://github.com/xigiy/CheeseJeans-Ai-Base.git
```

1. 打开浏览器扩展管理页面：
   · Chrome: chrome://extensions
   · Edge: edge://extensions
   · Firefox: about:debugging#/runtime/this-firefox
2. 开启「开发者模式」
3. 点击「加载已解压的扩展程序」，选择项目文件夹

方法二：从商店安装（待上架）

· Chrome 网上应用店：[链接待补充]

· Edge 加载项商店：[链接待补充]

· Firefox 附加组件商店：[链接待补充]

>测试中暂不提供

---

⚙️ 配置说明

首次使用配置

1. 点击插件图标 → 点击顶部的 ⚙️ 设置API 按钮
2. 填写你的 API 信息：

配置项 |说明 |示例
API 地址 |API 的基础 URL（末尾不加 /chat/completions）| https://api.mistral.ai/v1
API Key |你的 API 密钥 |xxxxxxxxxxxxx
模型名称 |要使用的模型 |mistral-small-latest

1. 点击「测试连接」验证配置是否正确
2. 点击「保存设置」完成配置

---

📖 使用指南

基础操作

1. 保存网页：
   · 打开任意网页
   · 点击插件图标
   · 可选：添加笔记和标签
   · 点击「保存到知识库」
   · AI 自动生成摘要并保存
2. 查看已保存内容：
   · 插件主界面下方显示最近保存的 20 条记录
   · 点击标题可在新标签页打开原文
3. 搜索内容：
   · 在搜索框输入关键词
   · 实时过滤标题、摘要、标签
4. 删除条目：
   · 点击条目右侧的「删除」按钮

---

🛠️ 技术栈

| 模块 | 技术 | 说明 |
|------|------|------|
| 核心引擎 | OpenAI 兼容 API | 支持任意兼容的 API 服务商 |
| 框架 | 原生 JavaScript (ES6+) | 无外部依赖 |
| 存储 | IndexedDB | 本地数据库存储 |
| 构建 | 无需构建 | 纯源码运行 |
| 兼容层 | WebExtension Polyfill | 跨浏览器支持 |
| UI | 原生 HTML/CSS | 轻量简洁 |

---

📁 项目结构

```
CheeseJeans-Ai-Base/
├── manifest.json              # 插件配置文件
├── popup/
│   ├── popup.html            # 主界面
│   ├── popup.js              # 主逻辑
│   └── popup.css             # 样式文件
├── options/
│   ├── options.html          # 设置页
│   └── options.js            # 设置逻辑
├── lib/
│   ├── db.js                 # 数据库操作
│   ├── api.js                # API调用封装
│   └── browser-polyfill.js   # 跨浏览器兼容层
├── icons/                     # 图标文件（可选）
├── README.md                  # 中文说明
├── README-en.md               # 英文说明
├── DISCLAIMER.md              # 免责声明
├── FAQ.md                     # 常见问题
└── LICENSE                    # 许可证
```

> 正在测试中，暂不提供文件

---

🤝 贡献

欢迎提交 Issue 和 PR，共同改进这个项目。

---

📮 联系

· B站：FL-xigiy
· GitHub：xigiy

---

🌏 语言 / Language

· 中文
· English

---

📅 最后更新：2026年3月 | 📄 版本：v1.0.0 | 🧀 芝士裤：你的私人知识助手