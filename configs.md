# 客户端配置速查

一份「地址 + 密钥」如何填进各种客户端。**最容易踩的坑：`/v1` 有的要带，有的不能带。**

> 懒人方案：用 [relay-converter](https://github.com/dafeiai918/relay-converter) 一键生成全部格式。

---

## 通用原则

```
你的中转站地址：https://api.example.com/v1
密钥：sk-xxxxxxxx
```

- 以 `/v1` 结尾的是**完整接口地址**
- 去掉 `/v1` 的是**根地址**
- 路径通常还要接 `/chat/completions`

---

## Cherry Studio

**位置**：设置 → 模型服务 → 添加提供商 → 类型选 `OpenAI`

```
API 地址   https://api.example.com        ← 不要带 /v1
API 密钥   sk-xxxxxxxx
```

添加模型时填模型 ID（如 `gpt-4o-mini`），点「检查」通过后保存。

> ⚠️ 带了 `/v1` 会连接失败，这是最常见的错误。

---

## NextChat

**位置**：设置 → 自定义接口

```
接口地址   https://api.example.com/v1
API Key    sk-xxxxxxxx
模型名     gpt-4o-mini
```

其他字段留空。

---

## Chatbox

**位置**：设置 → 模型 → 添加自定义提供方

```
API 域名   https://api.example.com
API 路径   /v1/chat/completions
API 密钥   sk-xxxxxxxx
模型名     gpt-4o-mini
```

域名和路径**分开填**，不要重复。

---

## Jan

**位置**：设置 → 模型 → 添加提供商 → OpenAI 兼容

```
Base URL   https://api.example.com/v1
API Key    sk-xxxxxxxx
模型 ID    gpt-4o-mini
```

---

## Open WebUI（自部署）

**方式一（界面）**：管理员设置 → 连接 → OpenAI API

```
URL        https://api.example.com/v1
Key        sk-xxxxxxxx
```

**方式二（环境变量）**：

```env
OPENAI_API_BASE_URL=https://api.example.com/v1
OPENAI_API_KEY=sk-xxxxxxxx
```

---

## LobeChat（自部署）

```env
OPENAI_API_KEY=sk-xxxxxxxx
OPENAI_PROXY_URL=https://api.example.com/v1
```

> 不设 `OPENAI_PROXY_URL` 时会走官方接口。

---

## LibreChat

**文件**：`librechat.yaml`

```yaml
version: 1
endpoints:
  custom:
    - name: "中转站"
      apiKey: "sk-xxxxxxxx"
      baseURL: "https://api.example.com/v1"
      models:
        default: ["gpt-4o-mini", "deepseek-chat"]
        fetch: true
      titleConvo: true
```

---

## Continue（VS Code / JetBrains）

**文件**：`~/.continue/config.json`

```json
{
  "models": [
    {
      "title": "中转站",
      "provider": "openai",
      "model": "gpt-4o-mini",
      "apiBase": "https://api.example.com/v1",
      "apiKey": "sk-xxxxxxxx"
    }
  ]
}
```

---

## Cline（VS Code）

**文件**：`settings.json`

```json
{
  "cline.apiProvider": "openai",
  "cline.openAiBaseUrl": "https://api.example.com/v1",
  "cline.openAiApiKey": "sk-xxxxxxxx",
  "cline.openAiModelId": "gpt-4o-mini"
}
```

---

## Aider（命令行）

**文件**：`.env` 或环境变量

```env
OPENAI_API_BASE=https://api.example.com/v1
OPENAI_API_KEY=sk-xxxxxxxx
```

用法：

```bash
aider --model openai/gpt-4o-mini
```

---

## Codex CLI

**文件**：`~/.codex/config.toml`

```toml
model = "gpt-4o-mini"
model_provider = "relay"

[model_providers.relay]
name = "Relay"
base_url = "https://api.example.com/v1"
wire_api = "chat"
env_key = "RELAY_API_KEY"
```

同时设环境变量 `RELAY_API_KEY=sk-xxxxxxxx`。

> ⚠️ **不要整体覆盖** `config.toml`，会丢掉你已有的 `projects` / `mcp_servers` 配置。只追加或修改对应字段。

---

## OpenCode

**文件**：`opencode.json`

```json
{
  "provider": {
    "relay": {
      "npm": "@ai-sdk/openai-compatible",
      "options": {
        "baseURL": "https://api.example.com/v1",
        "apiKey": "sk-xxxxxxxx"
      },
      "models": { "gpt-4o-mini": {} }
    }
  }
}
```

---

## AnythingLLM

**位置**：设置 → LLM 首选项 → 提供方选 `Generic OpenAI`

```
Base URL   https://api.example.com/v1
API Key    sk-xxxxxxxx
Chat Model gpt-4o-mini
```

---

## SillyTavern

**位置**：连接设置 → API 选 `Chat Completion` → 来源选 `Custom (OpenAI-compatible)`

```
Custom URL   https://api.example.com/v1
API Key      sk-xxxxxxxx
模型名        gpt-4o-mini
```

---

## Dify

**位置**：设置 → 模型供应商 → `OpenAI-API-compatible` → 添加模型

```
API Base URL   https://api.example.com/v1
API Key        sk-xxxxxxxx
模型名称        gpt-4o-mini
```

> ⚠️ Dify 许可证禁止移除其前端 LOGO。

---

## 通用 .env

```env
OPENAI_BASE_URL=https://api.example.com/v1
OPENAI_API_BASE=https://api.example.com/v1
OPENAI_API_KEY=sk-xxxxxxxx
OPENAI_MODEL=gpt-4o-mini
```

---

## 验证是否配好

```bash
# curl 测试
curl https://api.example.com/v1/chat/completions \
  -H "Authorization: Bearer sk-xxxxxxxx" \
  -H "Content-Type: application/json" \
  -d '{"model":"gpt-4o-mini","messages":[{"role":"user","content":"你好"}]}'
```

或直接用 [relay-bench](https://github.com/dafeiai918/relay-bench) 做完整体检。

---

## 排错清单

| 现象 | 原因 |
|---|---|
| 404 Not Found | 地址多了或少了 `/v1` |
| 401 Unauthorized | 密钥错误，或缺少 `Bearer ` 前缀 |
| 连不上 / 超时 | 网络问题，或站点不可用 |
| 模型不存在 | 模型名写错，或该站点没有此模型 |
| 返回空 | 部分中转站需要指定 `max_tokens` |

---

MIT · 欢迎补充你踩过的坑
