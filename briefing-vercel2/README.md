# Integrative Briefing Tool

AI-powered briefing guidance based on *Managing the Brief for Better Design* (Blyth & Worthington).

## File structure

```
api/
  chat.js        ← serverless function (holds your API key server-side)
index.html       ← the full tool
package.json
vercel.json
```

## Deploy to Vercel

### 1. Put the files on GitHub

1. Go to [github.com](https://github.com) → New repository (e.g. `briefing-tool`)
2. Upload all files — drag and drop into the GitHub interface, preserving the folder structure above
3. Commit

### 2. Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) → Add New → Project
2. Import your GitHub repository
3. **Important:** leave all build settings blank/default — do not set a framework preset
4. Click **Deploy**

### 3. Add your Anthropic API key

1. In the Vercel dashboard, go to your project → **Settings → Environment Variables**
2. Click **Add New**:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** your key from [console.anthropic.com](https://console.anthropic.com)
3. Click **Save**
4. Go to **Deployments** → click the three dots on the latest deployment → **Redeploy**

### 4. Share

Your tool is live at `https://your-project-name.vercel.app` — share with anyone.

---

## How it works

The browser calls `/api/chat` (your serverless function on Vercel), which forwards the request to Anthropic using the API key stored in Vercel's environment variables. The key is never exposed to the browser.
