[English](README.md) | [简体中文](README.zh-CN.md)

# Savault (知识桥梁)

Turn your own saved collections into knowledge-base notes: Xiaohongshu / Bilibili → Obsidian. Notion integration is still being improved and is not currently recommended as the primary sync destination.

- Website and download: https://product.aiprice.store/clipin/
- Free edition: a 50-item sync allowance (metadata + local cover images + frontmatter + incremental sync)
- Full-feature license code (free during beta; ¥99 for a one-time purchase in the official release): unlimited sync + Ask Your Collections (AI conversations with your collection library, BYOK) + transcripts + AI summaries
- Existing users: old `B2O-` / `CLP-` license codes remain valid; settings are automatically migrated when upgrading from the old bili2obsidian version

## Installation

1. Download `savault.zip` from the [latest Release](https://github.com/lin113311221/savault-plugin/releases)
2. Create `.obsidian/plugins/savault/` inside your Vault, then extract `main.js` / `manifest.json` / `styles.css` from the ZIP into that directory
3. In Obsidian → Settings → Community plugins → turn off Safe mode → refresh → enable “知识桥梁 Savault”
4. Configure platform credentials in the plugin settings (see the platform guides below)

> Upgrading from the old Bili2Obsidian version: settings (including the license code) in `.obsidian/plugins/bili2obsidian/` are automatically migrated when the new version first starts. The old directory is retained.

## Collection Without Pop-up Windows (Enabled by Default Since v0.5.66)

When the login session is valid, syncing **no longer opens the “Start reading” window**. The plugin reads data in an offscreen page and destroys it automatically after syncing, with no visible window throughout the process.

A login window appears only in three cases: session validation fails, the offscreen page cannot start, or no items are read (the plugin automatically retries once).

Turn off “免打扰采集” in settings to restore the previous behavior of showing a confirmation window for every sync.

## Platform Setup Guides

### Xiaohongshu

**Recommended: embedded login (the simplest option)**

Plugin settings → Xiaohongshu → click “登录” → scan the QR code in the pop-up window with the Xiaohongshu app → the plugin automatically saves the login session. You do not need to copy any cookie manually.

> Alternative: if embedded login is unavailable, copy the cookie manually: open xiaohongshu.com in your browser and log in → F12 → Network → select any request → copy the complete Cookie string from Request Headers → paste it into the Cookie field in settings.

### Bilibili

**QR-code login (recommended)**: plugin settings → Bilibili → click “扫码登录” → scan the displayed QR code with the Bilibili app → the plugin saves the session automatically. You do not need to find SESSDATA manually.

> Alternative: enter SESSDATA manually: log in to bilibili.com in your browser → F12 → Application → Cookies → copy and paste the value of `SESSDATA`.

## Optional Features

### Speech Transcription (Video → Transcript)

Transcribe the spoken content in video notes. An Alibaba Cloud Model Studio API Key is required:

1. Open the [Alibaba Cloud Model Studio console](https://bailian.console.aliyun.com/#/api-key) → log in (Alipay/Taobao accounts can be used)
2. Select “API-KEY” on the left → create a new API Key → copy the string starting with `sk-`
3. Paste it into plugin settings → “口播转写 dashscope Key”
4. Turn on “口播转写”

> Transcription uses Alibaba Cloud's Paraformer model and reads the video URL directly (without downloading the video). Check the provider console for fees and allowances; this version does not offer gifted cloud transcription minutes.

### Cloud AI Service Cards (v0.5.69)

If you have a redemption card starting with SVC_, paste it into “云端 AI 额度” in settings to redeem it. The service URL, personal Token, and model are configured automatically, and you can refresh the remaining allowance. Redeeming the same card again does not grant extra allowance. Keep the redemption card safe; it can recover the same service credentials.

Software licensing and AI allowances are calculated separately. Old license codes do not automatically receive cloud allowances. The cloud service remains subject to the site-wide test budget; plans and availability are governed by the confirmed delivery terms. Gifted cloud audio transcription is not available; users can configure their own SiliconFlow or DashScope Key for transcription separately.

### AI Summaries

Automatically generate the main ideas and key points during syncing. Use your own LLM API Key (BYOK):

1. Under “问答”, choose a provider: Qwen, GLM, MiniMax, Kimi, DeepSeek, SiliconFlow, or custom; presets automatically fill in the URL and model.
2. Enter that provider's API Key. A user-provided Key takes priority and connects directly; if no Key is entered, redeemed cloud text allowance is used.
3. Turn on “AI 总结”

### Sync Comments (Off by Default)

Read pinned/popular comments and render them in the note's “精选评论” section. Key information in many notes, such as links and tool names, appears in comments.

- Settings → turn on “同步评论” → the next sync collects comments item by item (off by default; it does not affect the body, transcription, or AI summaries)
- Xiaohongshu comments are **rendered into the DOM with the detail page**. The plugin reads them directly from the page without relying on an API, so collection is quick (35 items took about 2 extra minutes, with random intervals between items)
- Full comment collection has been enabled since v0.5.67. During v0.5.63~v0.5.66, collection was limited to the first 3 comments while testing whether “open detail page + scroll” would crash. Device testing succeeded in 3/3 cases with no crashes while scrolling, and the limit was removed

## Compliance

This plugin only syncs collections visible to your own account, and notes are saved locally. When AI is enabled, relevant content is sent to the configured service. Use it only for personal learning. Do not bulk-download or distribute other people's content, or bypass paywalls or access restrictions. Keep sync frequency reasonable and do not use it for commercial scraping.

## License

The plugin itself is proprietary software (paid features require activation with a license code). This repository is only for releases and feedback; Issues are welcome.

### Three AI Entry Points

- Transcription: supports SiliconFlow and DashScope only; native subtitles are read first.
- Image recognition: configure the provider and Key separately; at most the first 4 images in each note are recognized.
- Q&A: used for summaries and Ask Your Collections. The Qwen preset is qwen3.8-flash; gifted allowance uses the verified Qwen/Qwen3.5-35B-A3B.

The three entry points are configured independently; balances remain shared when using the same provider account. Switching providers does not send the old provider's Key to the new provider.

## Related Links

- [Dream Bridge Lab](https://github.com/dreambridgelab)
- [Savault Global](https://yourdreamlab.net/apps/savault/)

The Global product page is a separate entry point. This repository continues to document the original proprietary Obsidian plugin, its releases, and its applicable terms.
