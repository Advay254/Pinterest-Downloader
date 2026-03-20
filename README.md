# PinSaver

**A fast, free Pinterest video & image downloader. Self-host in one click.**

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)
&nbsp;
<a href="https://www.buymeacoffee.com/advay254" target="_blank"><img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-%E2%98%95-yellow?style=flat-square" alt="Buy Me A Coffee" /></a>

---

## What is PinSaver?

PinSaver is a self-hosted web app that lets you download Pinterest videos and images in their original quality — no watermarks, no limits, no sign-in required. Fork this repo, deploy it to your own server, and you get your own private Pinterest downloader running in minutes.

- ✅ Downloads Pinterest videos (MP4) and images (JPG/PNG)
- ✅ Supports `pin.it` short links and all regional Pinterest domains
- ✅ PWA-ready — works like a native app on mobile
- ✅ Built-in rate limiting
- ✅ AdSense / ad network integration hooks
- ✅ Android APK included in the web UI
- ✅ Blog pages for SEO

---

## How It Works

This public repo contains a lightweight launcher (`launcher.js`). When you deploy and start the app:

1. The launcher fetches the **latest production release** from the core repository.
2. It downloads and extracts the release package into a temporary working directory.
3. It installs dependencies automatically.
4. It starts the live application and passes through all your environment variables.

You never need to touch the core code. Updates to the core are picked up automatically on every fresh deploy.

---

## Staying Up to Date

Check [`version.txt`](./version.txt) to see the current public release version.

When the author publishes a new core release and bumps `version.txt`, fork-holders will see the change in their fork's network. To get the update:

1. **Sync your fork** with the upstream repo (GitHub → *Sync fork* button).
2. **Redeploy** your server (Render → *Manual Deploy → Deploy latest commit*).

The launcher always pulls the **latest** release automatically — no manual file replacements needed.

---

## Deploying to Render

> Render is recommended. Free tier works fine.

1. **Fork** this repository to your GitHub account.
2. Go to [render.com](https://render.com) → **New Web Service**.
3. Connect your forked repo.
4. Set the following:
   - **Runtime:** Node
   - **Build Command:** *(leave blank)*
   - **Start Command:** `npm start`
   - **Node Version:** `20`
5. Add your [environment variables](#environment-variables) under **Environment**.
6. Click **Deploy**.

---

## Environment Variables

Configure these in your hosting platform's environment settings. All variables are optional — the app runs with sensible defaults if they are not set.

| Variable | Description | Default |
|---|---|---|
| `PORT` | Port the HTTP server listens on | `3000` |
| `SITE_URL` | Your deployment URL (used for sitemap generation) | `https://pinsaver.onrender.com` |
| `AD_DECOY_1_URL` | Ad network interstitial URL #1 | *(empty)* |
| `AD_DECOY_2_URL` | Ad network interstitial URL #2 | *(empty)* |
| `AD_WAIT_URL` | Ad network wait/redirect URL | *(empty)* |
| `API_MASTER_KEY` | Master key to protect the internal API endpoints | *(empty)* |
| `RAPIDAPI_PROXY_SECRET` | Secret for RapidAPI proxy authentication | *(empty)* |

---

## Local Development

> You will need Node.js 20+ and `unzip` available on your system.

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/pinsaver.git
cd pinsaver

# Install launcher deps (none needed — launcher uses Node built-ins only)
# Just start it:
node launcher.js
```

Set environment variables in your shell before running, or use a `.env` loader of your choice.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Runtime | Node.js 20 (ESM) |
| HTTP framework | Express 4 |
| HTTP requests | node-fetch 3 |
| Archive | archiver 7 |
| Hosting | Render (recommended) |
| Frontend | Vanilla JS + Tailwind CDN |

---

## License

This project is source-available for personal and non-commercial self-hosting use only. Redistribution, reselling, or white-labelling this software without written permission from the author is not permitted.

---

## Support the Project

If PinSaver saves you time or money, consider supporting the developer:

<a href="https://www.buymeacoffee.com/advay254" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" width="200" />
</a>
