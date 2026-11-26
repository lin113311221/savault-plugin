[English](README.md) | [简体中文](README.zh-CN.md)

# 知识桥梁 Savault — 收藏整理与 AI 知识使用

## 下载与校验

[官网下载页](https://product.aiprice.store/savault/#downloads)提供 Windows x64 桌面版（含 CLI，0.1.10）、Mac 预览版（0.1.10，macOS 13+，Apple 芯片或 Intel）和桌面 Obsidian 插件（0.5.75）。抖音收藏同步和分享链接导入仍为预览功能，首次请先同步一条，打开笔记核对来源。

将下方命令中的 `YOUR-DOWNLOAD.zip` 换为实际文件名。解压前按 ZIP 完整文件名查[官网 SHA-256 清单](https://product.aiprice.store/savault/downloads/SHA256SUMS.txt)，用 Windows 的 `Get-FileHash ./YOUR-DOWNLOAD.zip -Algorithm SHA256` 或 macOS 的 `shasum -a 256 ./YOUR-DOWNLOAD.zip` 比对摘要。首次保存 Markdown 可按[本地文件夹入门](https://product.aiprice.store/savault/#local-guide)操作。

[GitHub v0.5.71 Release](https://github.com/lin113311221/savault-plugin/releases/tag/v0.5.71)保留较早的插件及其附件。需要复现该版本时可从这里下载。

把选定的小红书、B站收藏整理进 Obsidian，本仓库提供插件发行与问题反馈。Savault 另有 Windows/Mac 统一客户端（含 CLI），以及供 Agent 调用的收藏同步 Skill。

收藏中的写作方法、工作经验和学习资料，整理后可以授权给 Codex、WorkBuddy 等 AI 工具读取，用在你的具体任务里，并保留参考来源。

- [产品介绍、当前下载与教程](https://product.aiprice.store/savault/)
- [让 AI 用上收藏：Notion MCP / 本地 Markdown 接入指南](docs/ai-knowledge-workflow.md)
- [Savault Notion Agent Skill](https://github.com/lin113311221/savault-skills)
- [本仓库历史发行包](https://github.com/lin113311221/savault-plugin/releases)

## 先选入口

| 你要做什么 | 入口 |
|---|---|
| 把收藏存成本地笔记、使用内置“问收藏” | Obsidian 插件 |
| 把收藏存进本地文件夹、Notion 或 Obsidian | Windows/Mac 统一客户端，或收藏同步 Skill |
| 让 AI 阅读同步后的 Notion 笔记 | 另行授权 Notion MCP 或相应读取连接器 |
| 让 AI 阅读本地笔记 | 授予指定 Markdown 文件/文件夹读取权限 |

官网下载的桌面客户端和 Obsidian 插件都可使用内置“问收藏”，需有效 AI 权益。**没有在本公开仓库发布成问答 MCP**。同步 Skill 也不是问答 MCP。笔记不会自动训练模型或自动变成已安装的 Skill。

## 安装与第一次使用

1. 从产品页选择 Obsidian 插件下载，核对版本。这里的旧 Release 保留历史版本，不代表产品页当前版本。
2. 在 Vault 的 `.obsidian/plugins/savault/` 中放入包内的 `main.js`、`manifest.json` 和 `styles.css`。
3. 在 Obsidian 社区插件设置中启用“知识桥梁 Savault”。
4. 按设置提示完成平台登录并选择保存目录。登录和密钥输入在自己电脑上完成，不发送 Cookie 或密钥到 Issue/聊天。
5. 明确选择一个收藏夹，先同步一条，打开笔记核对正文与来源，再扩大范围。后续按需仅同步新增。

## 少拼流程，AI 服务可以自己选

Savault 把收藏选择、同步、转写、识图和总结放在同一套使用流程里。本地文件夹 / Notion / Obsidian 按你的习惯选择，按上面的步骤连接即可开始。

- 基础同步可先体验，累计新增 50 条；更新和跳过不占新增额度。
- AI 功能需有效付费授权，自带 API Key 也需要授权。
- 当前支持的功能可选择已兑换的服务额度，或配置自己的模型服务商 API Key。附赠额度有限，用完后按服务规则另计；自带 Key 的调用费由服务商收取。
- 转写、识图、文字问答分别有支持范围，不能把“自带 Key”理解为任意模型都可用。
- Savault 额度不包含 Codex、WorkBuddy 或 Notion 自身的订阅和模型费用。
- 已有模型套餐，可继续在套餐支持的 AI 工具里使用，并授权读取同步后的笔记；不代表 Savault 已支持直接通用 GLM、百炼或 Kimi 套餐，详见接入指南。

当前授权方案、购买状态、额度与版本以[产品页](https://product.aiprice.store/savault/)和对应版本说明为准；不沿用旧 README 的“内测免费领 / ¥99”口径。Mac 预览版未经 Apple 公证，首次打开请参阅官网下载页的说明。

## 使用边界与反馈

仅处理你有权访问的内容，尊重平台规则和原作者权利，不绕过访问限制或分发他人资料。启用 AI 时，相关内容会发送到所选模型服务。反馈请提供版本、复现步骤和脱敏错误，不提供账号凭证。

插件本体为专有软件，本仓库用于发行与反馈，不因公开仓库而变成开源运行时。Agent Skill 使用[固定的 Windows/Mac 0.1.6 运行包](https://github.com/lin113311221/savault-skills/releases/tag/desktop-v0.1.6)。本仓保留 Obsidian 插件的历史发行。

## Related links

- [Dream Bridge Lab](https://github.com/dreambridgelab)
- [Savault Global](https://yourdreamlab.net/apps/savault/)

Savault Global 是独立的英文 CLI，可将本人 YouTube 播放列表保存为 Markdown。本仓库分发 Obsidian 插件。

## 协作者与 Agent 接手

阅读 [agentconversation.md](agentconversation.md)，了解本仓职责、版本边界与接手步骤。英文 README 与本文同步维护。

使用独立分支提交 PR，说明目的和实际验证。默认分支要求 PR 与至少 1 人审核，禁止强推和删除，保留管理员例外。普通访客可以 Fork 和提议修改；写权限另行授予。

公开示例、Issue 和 Agent 接手记录不包含凭据、私人笔记或内部客户资料。
