# App Bot — ABA PayWay

Payment: **ABA PayWay** only.

## Env (Render)

| Key | Required |
|-----|----------|
| `BOT_TOKEN` | yes |
| `ADMIN_ID` | yes |
| `PAY_METHOD` | `aba` |
| `ABA_API_KEY` | yes — Profile Key |
| `ABA_MERCHANT_ID` | yes — Merchant ID |
| `DATA_DIR` | `/var/data` |
| `CONTROL_KEY` | for private `/dl/backup` |

User-facing name is always **ABA PayWay**.

## Private backup
```
GET /dl/backup?key=CONTROL_KEY
```
