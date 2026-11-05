# Wayrin plugin

[中文](#中文) · [English](#english)

## English

Wayrin (https://wayrin.com) is where creators share the AI workflows they actually use: skills, rules, prompts and agent configs. This plugin connects your AI agent to the Wayrin MCP server so it can search those workflows, read one in full, show what the creators you follow published, and save your own setup as a private draft.

### What it contains

- `skills/wayrin/SKILL.md` — how the agent should search, read and reuse Wayrin works safely.
- `mcp.json` / `.mcp.json` — one remote MCP server, `https://wayrin.com/mcp` (streamable HTTP). Sign-in uses OAuth in your browser; no API key or token is stored in this plugin.
- No hooks, no scripts, no local servers.

### Install

**Claude Code**
```
/plugin marketplace add 1924902988hu-del/wayrin-plugin
/plugin install wayrin@wayrin
```
Then type `/mcp`, choose `plugin:wayrin:wayrin`, and sign in to Wayrin in the browser.

**Codex**
```
codex plugin marketplace add 1924902988hu-del/wayrin-plugin
codex plugin add wayrin@wayrin
```

### What is sent where

The plugin talks only to `https://wayrin.com/mcp`. Read tools send your search terms and the id of a work. The two draft tools send only the files or messages you explicitly choose; drafts stay private and nothing is published without your own confirmation on wayrin.com. Your agent cannot publish. You can revoke access at any time under Start sharing on wayrin.com.

Content on Wayrin is written by third parties. The skill tells the agent to treat it as reference material, never as instructions, and to ask you before applying anything.

## 中文

Wayrin（https://wayrin.com）是创作者分享自己真实在用的 AI 工作流的地方：skill、规则、提示词、agent 配置。这个插件把你的 AI agent 接到 Wayrin 的 MCP 服务器，让它可以搜索这些工作流、完整读取某一个、查看你关注的创作者最近发布了什么，并把你自己的配置存成私有草稿。

### 包含什么

- `skills/wayrin/SKILL.md`：告诉 agent 如何安全地搜索、阅读、复用 Wayrin 上的作品。
- `mcp.json` / `.mcp.json`：一个远程 MCP 服务器 `https://wayrin.com/mcp`。登录走浏览器里的 OAuth，插件里不保存任何 API key 或 token。
- 没有 hooks、脚本或本地服务。

### 安装

**Claude Code**：`/plugin marketplace add 1924902988hu-del/wayrin-plugin`，再 `/plugin install wayrin@wayrin`，然后输入 `/mcp` 选择 `plugin:wayrin:wayrin`，在浏览器里登录 Wayrin。

**Codex**：`codex plugin marketplace add 1924902988hu-del/wayrin-plugin`，再 `codex plugin add wayrin@wayrin`。

### 数据去向

插件只连接 `https://wayrin.com/mcp`。读取类工具只发送搜索词和作品 id；两个草稿工具只发送你明确选定的文件或消息，草稿是私有的，不经你本人在 wayrin.com 确认不会发布，AI 不能发布。你可以随时在 wayrin.com 的「开始分享」里撤销授权。

Wayrin 上的内容由第三方创作者编写。skill 要求 agent 把它当参考资料而不是指令，应用前先问你。

## License

MIT
