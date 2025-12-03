# N8N Workflows Vault

Private repository for production N8N workflow JSON files.

> **Public portfolio:** [github.com/copywebltd/n8n-ai-workflows](https://github.com/copywebltd/n8n-ai-workflows)

---

## Folder Structure

```
workflows/
├── video-generation/       # AI video sub-workflows
├── image-generation/       # AI image sub-workflows
├── motion-ads/             # Motion Ads system
├── content-repurposing/    # Telegram-based repurposing
├── orchestrators/          # Main control workflows
└── utilities/              # Helper workflows
```

---

## How to Use

### Importing a Workflow

1. Download the `.json` file from this repo
2. In N8N: **Workflows** → **Import from File**
3. Select the downloaded file
4. Update credentials (they don't transfer)

### Exporting a Workflow

1. Open workflow in N8N
2. Click **⋮** (three dots menu) → **Download**
3. Rename file descriptively
4. Upload to appropriate folder here

---

## Naming Convention

```
[system]-[function]-[version].json

Examples:
- motion-ads-orchestrator-v2.json
- veo3-sub-workflow-v1.json
- content-repurposing-tiktok-to-sora-v1.json
```

---

## Credential Notes

⚠️ **Credentials are NOT included in exports** — this is intentional for security.

After importing, you'll need to reconnect:
- Kie.ai API key
- Google Sheets OAuth
- Telegram Bot token
- Blotato API key
- ElevenLabs API key

---

## Systems Index

### 1. AI Content Pipeline
*Google Sheets → Image Preview → Human Approval → Video Generation*

| Workflow | File | Description |
|----------|------|-------------|
| Image Orchestrator | `orchestrators/image-preview-orchestrator.json` | Routes to correct image model |
| Video Orchestrator | `orchestrators/video-generation-orchestrator.json` | Routes to correct video model |
| Seedream | `image-generation/seedream-v4.json` | ByteDance image generation |
| Nanobanana | `image-generation/nanobanana.json` | Google image enhancement |
| Nanobanana Pro | `image-generation/nanobanana-pro.json` | Multi-image compositing |
| VEO 3 | `video-generation/veo3.json` | Google video generation |
| Sora 2 | `video-generation/sora2.json` | OpenAI video generation |
| Kling | `video-generation/kling-v25.json` | Kuaishou video generation |
| Wan 2.5 | `video-generation/wan25.json` | Alibaba video generation |

### 2. Motion Ads System
*Single image → 9 motion video variations*

| Workflow | File | Description |
|----------|------|-------------|
| Motion Orchestrator | `motion-ads/motion-ads-orchestrator.json` | Main controller |
| VEO3 Motion | `motion-ads/veo3-motion.json` | Human motion videos |
| Kling Motion | `motion-ads/kling-motion.json` | Product motion videos |
| Batch Kling | `motion-ads/batch-kling-generator.json` | Parallel processing |

### 3. Content Repurposing Engine
*Telegram → Gemini Analysis → Scripts/Videos → Social*

| Workflow | File | Description |
|----------|------|-------------|
| TikTok → Sora | `content-repurposing/tiktok-to-sora.json` | Video remix generator |
| YT Short → Script | `content-repurposing/youtube-short-to-script.json` | Script generator |
| YT Long → Social | `content-repurposing/youtube-long-to-social.json` | LinkedIn/Twitter posts |

---

## Version History

| Date | Changes |
|------|---------|
| Dec 2024 | Initial upload - all production workflows |

---

## Security

- ✅ Repo is **private**
- ✅ No credentials in JSON files
- ✅ No API keys committed
- ⚠️ Don't make this repo public

---

*Maintained by Copyweb.io*
