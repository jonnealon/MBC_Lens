# MBC Lens - Render Deployment

## Setup on Render

1. Go to render.com and sign up with GitHub
2. Click **New** → **Web Service**
3. Connect your GitHub repo
4. Settings:
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
5. Add environment variable: `ANTHROPIC_API_KEY` = your key
6. Click **Create Web Service**

The service will deploy in 2-3 minutes and give you a URL like `mbc-lens-xxxx.onrender.com`
