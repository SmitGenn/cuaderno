# Cuaderno — Vocabulary Trainer

A personal spaced-repetition vocab trainer that works for **any language**.  
No account needed. No subscription. Your progress saves on your device.

## Features

- **20 languages** supported out of the box (Spanish, French, German, Japanese, Korean, Chinese, Arabic, Russian, and more)
- **Spaced repetition** (Leitner system) — the same algorithm behind Anki
- **Text-to-speech** pronunciation for every word
- **Paste-to-import** — generate cards with any AI, paste them in, done
- **PWA** — installs on your phone like a real app, works offline
- **Shareable** — send friends the URL, everyone gets their own progress

## What's in the box

```
cuaderno/
├── index.html      ← the entire app (one file, no build step)
├── manifest.json   ← PWA config (app name, icon, theme)
├── sw.js           ← service worker (offline caching)
├── icon-192.png    ← home screen icon
├── icon-512.png    ← splash screen icon
└── README.md       ← you're reading it
```

## Deploy in 5 minutes (free)

### Option A: Vercel (recommended)

1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Create a new repo on GitHub, push this folder to it:
   ```bash
   cd cuaderno
   git init
   git add .
   git commit -m "cuaderno v1"
   git remote add origin https://github.com/YOUR_USER/cuaderno.git
   git push -u origin main
   ```
3. In Vercel, click "Import Project" → select your repo → Deploy
4. Done. Your app lives at `cuaderno-xxxxx.vercel.app`
5. You can add a custom domain later if you want

### Option B: GitHub Pages (also free)

1. Push to GitHub (same steps as above)
2. Go to repo Settings → Pages → Source: "main" branch, root folder
3. Your app lives at `YOUR_USER.github.io/cuaderno`

### Option C: Netlify

1. Go to [netlify.com](https://netlify.com), drag the `cuaderno` folder onto the page
2. Done. Instant URL.

## Install on your phone

Once deployed, visit the URL on your phone:
- **iPhone**: tap Share (⬆️) → "Add to Home Screen"
- **Android**: tap the "Install" banner or Menu → "Add to Home Screen"

It opens fullscreen like a real app. Works offline after first load.

## How to add words

### The easy way (AI-generated)

1. In the app, tap **"Agregar palabras"**
2. Tap **"Show the prompt"** and copy it
3. Paste into Claude, ChatGPT, or any AI
4. Change `[YOUR TOPIC]` to whatever you want (e.g., "kitchen vocab", "PR slang")
5. Copy the AI's output
6. Paste it back into the app's import field
7. Preview → confirm → done, they're in your deck

### The format

One card per line, pipe-separated:

```
english | spanish | example in spanish | english translation of example
```

The last two fields (example + translation) are optional:

```
jam | la mermelada
to wake up | despertarse | Me despierto a las cinco. | I wake up at five.
nearby | cerca | El café está cerca. | The coffee shop is nearby.
```

### Manual

There's a "add one manually" dropdown at the bottom of the add screen  
for quick one-offs (English + Spanish, that's it).

## How to update

1. Come back to Claude and ask for changes
2. Copy the updated `index.html`
3. Replace the file in your repo
4. `git add . && git commit -m "update" && git push`
5. Vercel/GitHub Pages auto-deploys in ~30 seconds

## How the SRS works

Every word starts at **New** and climbs a rank ladder when you get it right:

| Rank | Next review |
|------|------------|
| I    | 1 day      |
| II   | 3 days     |
| III  | 7 days     |
| IV   | 16 days    |
| V    | 35 days    |
| Mastered | 90 days |

Get it wrong → drops back to Rank I (review tomorrow).  
This is the Leitner system — the same algorithm behind Anki.

## Share with friends

Just send them the URL. Each person's progress saves independently  
in their own browser (localStorage). Nothing syncs between users.
