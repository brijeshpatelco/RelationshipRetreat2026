# Deploying "The Reunion" to Vercel

This folder is a complete static website. No build step, no framework, no dependencies —
just `index.html` and an `assets/` folder. Any of the methods below will get it live.

```
the-reunion-site/
├── index.html          ← the page
├── assets/             ← images + video it references
│   ├── dinner.jpg
│   ├── group.jpg
│   ├── play.jpg
│   ├── barn.jpg
│   ├── albina.jpg  brijesh.jpg  fabi.jpg  rasa.jpg
│   ├── dance.mp4
│   └── dance-poster.jpg
└── DEPLOY.md           ← this file
```

Keep `index.html` and the `assets/` folder together. Don't rename `assets/`.

---

## Option 1 — Vercel Drop (easiest, no account setup beyond signing in)

1. Go to https://vercel.com/drop
2. Sign in (free "Hobby" plan is fine).
3. Drag this whole folder onto the page.
4. Pick a project name, then click **Deploy**.
5. In a few seconds you get a live URL like `the-reunion.vercel.app`.

That's it. Best for getting it live fast.

## Option 2 — Vercel CLI (no Git needed)

1. Install Node.js (https://nodejs.org) if you don't have it.
2. In a terminal:
   ```
   npm i -g vercel
   cd path/to/the-reunion-site
   vercel
   ```
3. Answer the prompts (accept the defaults). It deploys and prints your URL.
4. To push a production deploy later: `vercel --prod`.

## Option 3 — GitHub + Vercel (best if you'll keep editing)

1. Create a new GitHub repo and upload these files (index.html at the root).
2. At https://vercel.com/new, import that repo.
3. Framework preset: **Other**. Leave build command empty. Output directory: `.`
4. Click **Deploy**. From now on, every push to GitHub auto-deploys.

---

## Custom domain

In the Vercel dashboard: Project → **Settings → Domains** → add your domain and follow
the DNS instructions. HTTPS is set up automatically and is free.

## Editing later

- Text and colors live in `index.html` (the palette is the `:root { ... }` block near the top).
- To swap a photo, replace the matching file in `assets/` (keep the same filename), or update
  the `src="assets/..."` reference in `index.html`.
- Redeploy with the same method you used above.

## Note on the video

`assets/dance.mp4` is a compressed 720p version (~2.5 MB) so the page loads fast.
It autoplays muted and loops; visitors can turn sound on with the button on the video.
