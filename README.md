[English](README.md) | [简体中文](README.zh-CN.md)

# Savault — Saved collections for your knowledge base and AI

## Windows unified 0.1.6

[Download package and checksums](https://github.com/lin113311221/savault-skills/releases/tag/desktop-v0.1.6) · [Local folder guide](docs/local-folder.md)

One Windows package includes GUI and CLI, with local Markdown, Notion and Obsidian destinations. Local mode needs no note-taking app; grant your AI tool folder access after syncing. GUI and CLI profiles remain separate. Mac retains its earlier packages.


Organize selected Xiaohongshu and Bilibili collections into local Obsidian notes. This repository distributes the proprietary plugin and tracks issues. Savault also offers a Windows unified desktop/CLI and a collection-sync Agent Skill.

After you authorize a compatible AI host to read your notes, Codex, WorkBuddy, or another tool can use the methods and sources you saved in a concrete task.

- [Product, current downloads, and tutorials](https://product.aiprice.store/savault/)
- [AI setup guide: Notion MCP and local Markdown](docs/ai-knowledge-workflow.md)
- [Savault Notion Agent Skill](https://github.com/lin113311221/savault-skills)
- [Historical plugin releases](https://github.com/lin113311221/savault-plugin/releases)

## Choose an interface

| Task | Interface |
|---|---|
| Save local notes and use built-in Ask Your Collections | Obsidian plugin |
| Sync into Notion | Windows unified app or collection-sync Skill |
| Let an Agent read synced Notion pages | Separately authorized Notion MCP or another read connector |
| Let an Agent read local notes | Access to selected Markdown files/folders |

Built-in Ask Your Collections is currently available only in the Obsidian plugin. **This repository does not publish it as a Q&A MCP server.** The sync Skill is not a Q&A MCP either. Importing notes does not train a model or automatically install them as Agent Skills.

## Install and try one item

1. Select the Obsidian download on the product page and check its version. Historical GitHub releases may be older than the current product download.
2. Place `main.js`, `manifest.json`, and `styles.css` in your vault's `.obsidian/plugins/savault/` directory.
3. Enable Savault in Obsidian's community plugin settings.
4. Complete platform login locally and select the destination. Never post credentials in chat or Issues.
5. Explicitly select a collection, sync one item, and open the note to check content and source before expanding the selection. Use incremental sync when appropriate.

## AI service choice and costs

Savault combines collection selection, syncing, transcription, image understanding, and summaries in one workflow. Choose local Markdown, Notion or Obsidian to suit your habits and follow the connection steps above.

- Basic sync allows 50 newly created items; updates and skips do not consume that creation allowance.
- AI features require an active paid entitlement, even with your own API key.
- Supported features can use redeemed Savault service credits or your own provider key. Gift credits are finite; provider charges apply separately to BYOK usage.
- Transcription, vision, and text/Q&A have distinct provider/model compatibility. BYOK does not mean any model will work.
- Savault credits do not cover Codex, WorkBuddy, or Notion subscriptions or model usage.
- Keep using an existing model plan in a provider-supported AI client and authorize that client to read your notes. This does not establish direct Savault compatibility with GLM, Bailian, or Kimi plans; see the connection guide.

See the [product page](https://product.aiprice.store/savault/) and matching release notes for current licensing, purchase availability, allowances, and versions. The old beta-free / ¥99 wording no longer describes current offers. The Mac Notion client is currently a preview.

## Use and feedback

Process only content you may access, follow platform rules, and respect authors' rights. Do not bypass access restrictions or redistribute others' material. AI features may send relevant content to the selected model provider. Include version, reproduction steps, and redacted errors in Issues; exclude credentials.

The plugin remains proprietary. This public distribution repository does not open-source the runtime. The Windows unified runtime is distributed by savault-skills; this repository retains the separate Obsidian plugin releases.

## Related links

- [Dream Bridge Lab](https://github.com/dreambridgelab)
- [Savault Global](https://yourdreamlab.net/apps/savault/)

The Global page is a separate entry point; this repository documents the Obsidian plugin and its applicable terms.
