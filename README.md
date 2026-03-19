# Augmented Physics — Vercel Deploy

Interactive physics simulations from textbook diagrams, powered by Claude.

## Deploy in 3 steps

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Augmented Physics"
gh repo create augmented-physics --public --push
```

### 2. Connect to Vercel
- Go to https://vercel.com/new
- Import your GitHub repo
- Click **Deploy** (no build settings needed)

### 3. Add your API key
- In Vercel dashboard → your project → **Settings → Environment Variables**
- Add: `ANTHROPIC_API_KEY` = `sk-ant-...`
- Go to **Deployments** → click ⋯ → **Redeploy**

That's it. Your app is live at `https://your-project.vercel.app`

---

## Project structure

```
├── index.html       # Frontend (the Augmented Physics UI)
├── api/
│   └── proxy.js     # Serverless function — proxies requests to Anthropic
├── vercel.json      # Rewrites /v1/messages → /api/proxy
└── README.md
```

## Local development (optional)
```bash
npm i -g vercel
vercel dev
# Open http://localhost:3000
# Vercel dev auto-loads ANTHROPIC_API_KEY from .env.local
```

Create `.env.local`:
```
ANTHROPIC_API_KEY=sk-ant-...
```
