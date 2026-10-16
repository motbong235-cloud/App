# APSARA SMM BOT — Deploy on Render

## Files
- `kaijaklike_bot.py` — main bot
- `requirements.txt` — Python deps
- `render.yaml` — Render blueprint

## 1) Push to GitHub
```bash
cd ~/Kai-   # or new folder
unzip -oq apsara-smm-render-full.zip -d .
git add kaijaklike_bot.py requirements.txt requirements-bot.txt render.yaml README.md
git commit -m "APSARA SMM BOT full deploy package"
git push
```

## 2) Render
1. [render.com](https://dashboard.render.com) → **New** → **Web Service**
2. Connect repo `motbong235-cloud/Kai-` (or your repo)
3. Settings:
   - **Runtime:** Python 3
   - **Build:** `pip install -r requirements.txt`
   - **Start:** `python kaijaklike_bot.py`
   - **Health:** `/health`
4. **Disk** (important): mount `/var/data` size 1GB+
5. **Env vars:**

| Key | Value |
|-----|--------|
| `BOT_TOKEN` | from @BotFather |
| `ADMIN_ID` | your Telegram numeric ID |
| `BOT_DISPLAY_NAME` | `APSARA SMM BOT` |
| `DATA_DIR` | `/var/data` |
| `PAY_METHOD` | `khpay` (ទូទាត់ KHPAY តែមួយគត់) |
| `KHPAY_API_KEY` | **required** — Key ពី khpay.site |
| `KHPAY_MERCHANT_ID` | optional (`mch_...`) — ទុកទទេ = ប្រើ merchant លំនាំដើម |
| `BAKONG_API_TOKEN` | optional — សម្រាប់ប៊ូតុងបើក App ធនាគារ |

6. **Create Web Service** → wait deploy green

## 3) After deploy
1. Open bot in Telegram → `/start`
2. Admin: Setup Order Bot / Payment Bot (token + `/start` on those bots)
3. Add services / packages from admin menu

## Notes
- Plan **Starter** (or free) — free sleeps; use Starter for 24/7
- Without Disk, data resets every redeploy
- Payment: **KHPAY only** — CamRapidPay / ABA PayWay are disabled in this build
- Clone bot (`/newbot`) is disabled in this build
