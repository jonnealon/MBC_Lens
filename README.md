# MBC Lens - Migrant Body Commodification Analysis Tool

An analytical instrument for applying Migrant Body Commodification theory to immigration enforcement operations.

**Theoretical framework by Jon Nealon**

## Deployment Instructions

### 1. Get an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up or log in
3. Navigate to API Keys
4. Create a new key and copy it (you won't see it again)

### 2. Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `mbc-lens` (or whatever you prefer)
3. Keep it public or private (either works)
4. Don't initialize with README (we'll push our files)
5. Click "Create repository"

### 3. Push Code to GitHub

From your terminal in the project directory:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mbc-lens.git
git push -u origin main
```

### 4. Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) and sign up/log in with GitHub
2. Click "Add New Project"
3. Import your `mbc-lens` repository
4. Before deploying, click "Environment Variables"
5. Add: `ANTHROPIC_API_KEY` = (paste your API key)
6. Click "Deploy"

### 5. Done!

Vercel will give you a URL like `mbc-lens.vercel.app`. The tool is now live and runs on your own API quota, completely independent of Claude.ai usage.

## Project Structure

```
mbc-lens/
├── index.html      # The full React application
├── api/
│   └── analyze.js  # Serverless function that proxies API calls
├── vercel.json     # Vercel deployment configuration
└── README.md       # This file
```

## How It Works

- The frontend (`index.html`) is a single-page React app
- When users submit text for analysis, it calls `/api/analyze`
- The serverless function (`api/analyze.js`) adds your API key and forwards requests to Anthropic
- Your API key stays secure on the server, never exposed to browsers

## Cost Estimate

Each analysis uses Claude Sonnet and typically costs $0.01-0.05 depending on input length. URL fetching adds a small additional cost. With Anthropic's pay-as-you-go pricing, casual use might cost a few dollars per month.

## Custom Domain (Optional)

In Vercel dashboard → Settings → Domains, you can add a custom domain like `lens.yourdomain.com`.
