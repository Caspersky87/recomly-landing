# recomly-landing
Recomly landing page

## Store links

- App Store: https://apps.apple.com/app/id6772970281
- Google Play: https://play.google.com/store/apps/details?id=com.recomly.app

## `/download` (QR code target)

Sends phones to their store; other devices see both store buttons.

- `vercel.json` redirects iPhone and Android (except Huawei) on the server.
- The script in `download.html` catches iPads, which send a Mac user agent.

## `/business/download` (Recomly Business QR code target)

Same as `/download`, for Recomly Business (App Store id6835423379, Play `com.recomly.business`). The printed QR code points to `https://recomly.app/business/download?utm_source=qr`, so this path must never change. `business/qr-download.svg` is that code.

## Homepage

Store buttons in the hero and the download section. Phones see only their store; desktop sees both plus `qr-download.svg` (points to `https://recomly.app/download`).

## `/v/<code>` (guest visit QR, Recomly Business)

With Recomly Business installed, the link opens the app (iOS associated domains, Android app link via the files in `.well-known/`). Without it, `vercel.json` sends Android to Play and everything else to the App Store. The page never redeems the code.
