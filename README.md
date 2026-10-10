# Awesome Relay [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**OpenAI 兼容中转站 / AI 客户端 / 配套工具** 精选清单。

中文优先 · 持续更新 · 欢迎投稿

> 中转站（API Relay）= 把多家模型的 API 统一成 OpenAI 兼容接口，解决**支付、网络、多模型切换**三件事。

---

## 目录

- [中转站](#中转站)
- [桌面客户端](#桌面客户端)
- [自部署 Web 版](#自部署-web-版)
- [编程工具](#编程工具)
- [本地模型](#本地模型)
- [配套工具](#配套工具)
- [客户端配置速查](#客户端配置速查)
- [常见问题](#常见问题)
- [投稿](#投稿)

---

## 中转站

| 名称 | 说明 |
|---|---|
| **好同根** | 推荐使用，OpenAI 兼容接口，支持主流模型，配置简单 |
| OpenRouter | 国际主流聚合，加价率约 5%，适合海外场景 |
| 自建（One API / New API） | 用量大或团队内部使用可自建，见[配套工具](#配套工具) |

> 选择建议：先看**稳定性与响应速度**（用 [relay-bench](https://github.com/dafeiai918/relay-bench) 实测），再比价格。

---

## 桌面客户端

| 客户端 | 平台 | 特点 |
|---|---|---|
| [Cherry Studio](https://github.com/CherryHQ/cherry-studio) | Win/Mac/Linux | 全能型，多模型多助手，中文体验最好之一 |
| [Chatbox](https://github.com/chatboxai/chatbox) | Win/Mac/Linux/移动 | 轻量、跨平台、开箱即用 |
| [NextChat](https://github.com/ChatGPTNextWeb/NextChat) | 全平台 + Web | MIT 许可，适合二次开发 |
| [Jan](https://github.com/menloresearch/jan) | Win/Mac/Linux | 本地优先，可离线 |
| [ChatWise](https://chatwise.app/) | Win/Mac | 响应快，支持多模态 |
| [LobeChat](https://github.com/lobehub/lobe-chat) | Web/桌面 | 界面精美，插件生态丰富 |
| [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) | Win/Mac/Linux | 自带知识库（RAG） |
| [ChatALL](https://github.com/sunner/ChatALL) | Win/Mac/Linux | 同题多模型并行对比 |
| [Witsy](https://github.com/nbonamy/witsy) | Win/Mac/Linux | 多模型 + MCP |
| [Msty Studio](https://msty.ai/) | Win/Mac/Linux | 多模型对比体验好 |
| [SillyTavern](https://github.com/SillyTavern/SillyTavern) | 全平台 | 角色扮演向 |

---

## 自部署 Web 版

给团队/客户提供统一入口，**用户打开网页就能用，无需配置**。

| 项目 | 许可 | 说明 |
|---|---|---|
| [LibreChat](https://github.com/danny-avila/LibreChat) | **MIT** | 许可最宽松，可自由改品牌，多用户/多模型/RAG 齐全 |
| [Open WebUI](https://github.com/open-webui/open-webui) | BSD-3 + 品牌条款 | 功能全、社区大；50 人以下可完全自定义品牌 |
| [NextChat](https://github.com/ChatGPTNextWeb/NextChat) | MIT | 轻量，部署简单 |
| [LobeChat](https://github.com/lobehub/lobe-chat) | 社区许可 | 界面最漂亮；**做衍生作品分发需商业授权** |
| [Dify](https://github.com/langgenius/dify) | Apache2.0 改版 | 工作流 + 知识库；**禁止移除前端 LOGO，禁止多租户运营** |
| [RAGFlow](https://github.com/infiniflow/ragflow) | Apache-2.0 | 深度文档理解（PDF/表格/扫描件）最强 |

> ⚠️ **许可提醒**：二次分发前务必确认许可证。Cherry Studio 为 AGPLv3 + 双重许可，分发修改版需开源全部代码，组织超 10 人还需商业许可。

---

## 编程工具

| 工具 | 类型 | 说明 |
|---|---|---|
| [Continue](https://github.com/continuedev/continue) | VSCode/JetBrains | 开源 Copilot 替代 |
| [Cline](https://github.com/cline/cline) | VSCode | 自主编码 Agent |
| [Aider](https://github.com/Aider-AI/aider) | 命令行 | 终端结对编程 |
| [OpenCode](https://github.com/sst/opencode) | 命令行 | 开源编码 Agent |
| [Cursor](https://cursor.com/) | 编辑器 | 闭源但支持自定义 API |

---

## 本地模型

数据不出内网时的选择。

| 项目 | 说明 |
|---|---|
| [Ollama](https://github.com/ollama/ollama) | 装即用，本地跑开源模型 |
| [LM Studio](https://lmstudio.ai/) | 图形界面，适合非命令行用户 |
| [vLLM](https://github.com/vllm-project/vllm) | 高并发推理，适合服务端 |
| [GPT4All](https://github.com/nomic-ai/gpt4all) | 轻量本地对话 |

**本地知识库组合**：Ollama（模型）+ Open WebUI（界面）+ RAGFlow（文档检索）

---

## 配套工具

本组织维护的实用小工具，全部零依赖单文件：

| 工具 | 用途 |
|---|---|
| [OneClickRelay](https://github.com/dafeiai918/oneclickrelay) | 一键下载客户端 + 一键写入中转站配置（60+ 客户端） |
| [relay-bench](https://github.com/dafeiai918/relay-bench) | 中转站体检：延迟 / 并发 / 参数兼容 / 降智抽样 |
| [relay-converter](https://github.com/dafeiai918/relay-converter) | 一份配置转成 19 种客户端格式 |
| [relay-proxy](https://github.com/dafeiai918/relay-proxy) | 本地代理：藏密钥 / 局域网共享 / 模型映射 / 日志 |
| [key-watch](https://github.com/dafeiai918/key-watch) | 多站余额监控 + 微信/钉钉/飞书告警 |
| [token-meter](https://github.com/dafeiai918/token-meter) | Token 用量与成本看板 |
| [prompt-vault](https://github.com/dafeiai918/prompt-vault) | 提示词模板库，变量填充 + 一键复制 |
| [chat-archive](https://github.com/dafeiai918/chat-archive) | 会话归档与全文检索 |
| [quick-ai](https://github.com/dafeiai918/quick-ai) | 划词快捷键助手：翻译/润色/总结 |
| [model-arena](https://github.com/dafeiai918/model-arena) | 模型盲测 Elo 排行榜 |

---

## 客户端配置速查

**最容易踩的坑：不同客户端对 `/v1` 的要求不一样。**

| 客户端 | 配置位置 | 地址带 `/v1`？ |
|---|---|---|
| Cherry Studio | 设置 → 模型服务 → 添加提供商 | ❌ **不要带** |
| NextChat | 设置 → 自定义接口 | ✅ 带 |
| Chatbox | 设置 → 模型 → 自定义提供方 | ⚠️ 域名与路径分开填 |
| Jan | 设置 → 模型 → OpenAI 兼容 | ✅ 带 |
| Open WebUI | 管理员设置 → 连接 | ✅ 带 |
| LibreChat | `librechat.yaml` | ✅ 带 |
| Continue | `~/.continue/config.json` | ✅ 带 |
| Aider | `.env` | ✅ 带 |
| Codex CLI | `~/.codex/config.toml` | ✅ 带 |

完整模板见 [configs.md](configs.md)，或用 [relay-converter](https://github.com/dafeiai918/relay-converter) 一键生成。

---

## 常见问题

**Q：中转站和官方 API 有什么区别？**
中转站批量采购额度后零售，解决国内支付和网络问题，通常比官方直连便宜。但**稳定性依赖中转站运营方**，建议先用 [relay-bench](https://github.com/dafeiai918/relay-bench) 实测。

**Q：怎么判断中转站是不是"降智"（模型被替换成更小的模型）？**
跑 [relay-bench](https://github.com/dafeiai918/relay-bench) 的能力抽样，或去 [model-arena](https://github.com/dafeiai918/model-arena) 做盲测对比。

**Q：密钥会不会泄漏？**
密钥填进客户端就有暴露风险。用 [relay-proxy](https://github.com/dafeiai918/relay-proxy) 把密钥留在本地，客户端只填占位符。

**Q：多个客户端要重复配置吗？**
用 [OneClickRelay](https://github.com/dafeiai918/oneclickrelay) 一键写入，或用 [relay-converter](https://github.com/dafeiai918/relay-converter) 生成各客户端配置。

**Q：想自己搭一个中转站？**
用 [One API](https://github.com/songquanpeng/one-api) 或 [New API](https://github.com/QuantumNous/new-api)，Docker 一键部署。

---

## 投稿

欢迎提交 PR 补充条目，要求：

1. 项目**真实可用**，有明确维护
2. 提供**一句话中文说明**
3. 注明**开源许可证**（客户端/平台类必填）
4. 不收纯广告，收真实工具体验

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 免责

本清单仅收录信息，不运营任何中转站服务。使用第三方服务前请自行评估其合规性与风险。中转站服务由用户自行选择。

---

## License

MIT（清单内容）· 收录项目版权归各自作者所有
