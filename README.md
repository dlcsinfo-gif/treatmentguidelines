# NACO AI Chatbot — Deployment Guide

## What's included
- `index.html` — Complete chatbot web app (no build step needed)
- `vercel.json` — Vercel deployment config

---

## Step 1: Get a free Gemini API key
1. Go to https://aistudio.google.com/apikey
2. Sign in with any Google account
3. Click **"Create API Key"**
4. Copy the key (starts with `AIza…`)

---

## Step 2: Deploy to Vercel (free, 5 minutes)

### Option A — GitHub (recommended)
1. Create a free account at https://github.com
2. Create a new repository called `naco-chatbot`
3. Upload both files (`index.html` and `vercel.json`) to the repo
4. Go to https://vercel.com and sign up with your GitHub account
5. Click **"Add New Project"** → import your `naco-chatbot` repo
6. Click **Deploy** — no settings to change
7. Vercel gives you a URL like: `https://naco-chatbot.vercel.app`

### Option B — Vercel CLI (faster)
```bash
npm i -g vercel
cd /path/to/naco-chatbot
vercel --prod
```

---

## Step 3: Paste URL in Admin Panel
1. Go to your NACO admin panel → Other Resources
2. Section Name: `AI Chatbot`
3. Add Link: `https://naco-chatbot.vercel.app` (your Vercel URL)
4. Toggle Status: ON
5. Click **Proceed To Submit**

---

## Step 4: First time use
When a user opens the chatbot link, they will be prompted to enter
their Gemini API key once. It gets saved in their browser —
they never need to enter it again.

---

## Free tier limits (Gemini 1.5 Flash)
- 15 requests per minute
- 1 million tokens per day
- No credit card required

---

## Updating the PDF
No action needed — the chatbot always fetches the live PDF URL:
`https://treatandcareguide.naco.gov.in//admin/pdf/guidelines.pdf`

When you update the PDF on your server, the chatbot automatically 
uses the new version on the next query.

---

## Adding more PDFs
Open `index.html`, find the line:
```js
const PDF_URL = 'https://treatandcareguide.naco.gov.in//admin/pdf/guidelines.pdf';
```
You can extend this to an array and pass multiple PDFs to Gemini.
Contact your developer for this enhancement.
