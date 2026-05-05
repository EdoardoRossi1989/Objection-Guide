# Objection Handling Guide Builder
## Deployment Guide — Step by step

This tool uses the Anthropic API to generate sales guides. The proxy keeps your API key
secure on the server rather than exposed in the browser.

---

## What's in this folder

```
/
├── index.html        ← The tool itself (your front-end)
├── api/
│   └── proxy.js      ← The secure server that holds your API key
├── vercel.json       ← Vercel configuration
└── .env.example      ← Template for your API key (don't commit the real one)
```

---

## Deploy in 5 steps (~10 minutes, free)

### Step 1 — Create a GitHub account
Go to https://github.com and sign up if you don't have one.

### Step 2 — Create a new repository
1. Click the "+" icon top-right → "New repository"
2. Name it something like `objection-guide`
3. Set it to **Private**
4. Click "Create repository"
5. Upload all files from this folder (drag and drop works on GitHub)

### Step 3 — Create a Vercel account
Go to https://vercel.com and sign up with your GitHub account.

### Step 4 — Deploy from GitHub
1. On Vercel dashboard, click "Add New Project"
2. Select your `objection-guide` repository
3. Click "Deploy" — Vercel detects the config automatically
4. Wait ~30 seconds for the first deploy to complete

### Step 5 — Add your API key
1. In Vercel, go to your project → Settings → Environment Variables
2. Click "Add New"
3. Name: `ANTHROPIC_API_KEY`
4. Value: your Anthropic API key (starts with `sk-ant-...`)
   → Get one at https://console.anthropic.com
5. Click Save
6. Go to Deployments → click the three dots → "Redeploy"

Your tool is now live at `https://your-project-name.vercel.app`

---

## Getting your Anthropic API key

1. Go to https://console.anthropic.com
2. Sign up or log in
3. Go to "API Keys" in the left menu
4. Click "Create Key"
5. Copy the key immediately — you can only see it once
6. Paste it into Vercel as described in Step 5

Anthropic charges per use. Generating one guide costs roughly $0.05–0.15
depending on the length of inputs. You can set spend limits in the console.

---

## Running locally (optional)

If you want to test on your own computer before deploying:

1. Install Node.js from https://nodejs.org
2. Install Vercel CLI: `npm i -g vercel`
3. In this folder, create a file called `.env.local` and add:
   `ANTHROPIC_API_KEY=sk-ant-your-key-here`
4. Run: `vercel dev`
5. Open http://localhost:3000

---

## Updating the tool

To make changes to the tool after deployment:
1. Edit `index.html` locally
2. Upload the updated file to GitHub (replace the existing one)
3. Vercel automatically redeploys within ~30 seconds

---

## Connecting a custom domain (optional)

In Vercel → your project → Settings → Domains → Add your domain.
Follow the DNS instructions Vercel provides. Takes 5–10 minutes to propagate.
