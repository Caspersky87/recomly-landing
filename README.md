# recomly-landing
Recomly waitlist landing page

## `/download` (QR code target)

Before launch it shows "coming soon" with a waitlist link. To go live once both store listings are public:

1. In `download.html`, set `var LIVE = true;`.
2. Add these redirects to `vercel.json` so phones skip the page:

```json
"redirects": [
  {
    "source": "/download",
    "has": [{ "type": "header", "key": "user-agent", "value": ".*(iPhone|iPod).*" }],
    "destination": "https://apps.apple.com/app/id6772970281",
    "permanent": false
  },
  {
    "source": "/download",
    "has": [{ "type": "header", "key": "user-agent", "value": ".*Android.*" }],
    "missing": [{ "type": "header", "key": "user-agent", "value": ".*HuaweiBrowser.*" }],
    "destination": "https://play.google.com/store/apps/details?id=com.recomly.app",
    "permanent": false
  }
]
```
