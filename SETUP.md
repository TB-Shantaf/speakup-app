# SpeakUp — Complete Setup Guide

## What you'll get
A working English voice-coaching web app with:
- Real microphone input (Speech-to-Text)
- AI conversation partner that actually responds
- AI replies spoken out loud (Text-to-Speech)
- Live coaching tips
- Beautiful mobile-first UI
- Text input fallback if microphone doesn't work

---

## Step 1: Create a NEW GitHub repository

1. Go to **github.com**
2. Click the **"+"** button in the top-right corner
3. Click **"New repository"**
4. Name it: **`speakup`** (or any name you like)
5. Choose **Public**
6. Click **"Create repository"**

**Do NOT use the old repo. Start completely fresh.**

---

## Step 2: Upload the THREE files

You will receive three files in this exact structure:

```
your-repo/
├── index.html
├── vercel.json
└── api/
    └── chat.js
```

### How to upload them on GitHub:

1. On the new empty repository page, click **"uploading an existing file"** link
2. Drag and drop **`index.html`** and **`vercel.json`** into the upload area
3. Click **"Commit changes"** at the bottom

### Now create the api folder with chat.js:

1. On the repo page, click **"Add file"** → **"Create new file"**
2. In the filename box, type exactly: **`api/chat.js`**
   (the slash creates the folder automatically)
3. Paste the contents of `chat.js` into the editor
4. Click **"Commit changes"**

Your repository should now look like this:
- ✅ index.html
- ✅ vercel.json
- ✅ api/ (folder)
  - ✅ chat.js

---

## Step 3: Connect to Vercel

1. Go to **vercel.com**
2. Click **"Add New..."** → **"Project"**
3. Find your **speakup** repo and click **"Import"**
4. **DO NOT click Deploy yet!**

### Add the API key BEFORE deploying:

1. Expand the **"Environment Variables"** section
2. Add this variable:
   - **Key:** `ANTHROPIC_KEY`
   - **Value:** your `sk-ant-api03-...` key from Anthropic
3. Click **"Add"**
4. Now click **"Deploy"**

Wait 1-2 minutes for the deployment to finish.

---

## Step 4: Test it

1. Click **"Visit"** to open your app
2. Allow microphone access when the browser asks
3. Tap "Start Speaking"
4. Complete the 3 onboarding steps
5. Tap the green **CTA card** to start a session
6. Tap the microphone and speak — or use the text input if mic doesn't work

---

## Common Issues & Fixes

### Issue: AI replies "Connection error" or doesn't respond

**Cause:** Environment variable not set correctly.

**Fix:**
1. Go to Vercel project → **Settings** → **Environment Variables**
2. Verify the key is exactly `ANTHROPIC_KEY` (no `NEXT_PUBLIC_` prefix)
3. Make sure all 3 environments are checked: Production, Preview, Development
4. Go to **Deployments** → click the latest one → **"..."** → **"Redeploy"**

### Issue: Microphone doesn't work

**Causes:**
- Browser doesn't support Speech Recognition (Safari on iOS doesn't fully support it)
- User didn't allow mic access

**Fix:**
- Use Chrome or Edge browser
- Check browser address bar for the microphone permission icon
- The text input below the mic always works as a fallback

### Issue: AI voice doesn't speak

**Cause:** Browser blocked auto-playing audio until user interacts.

**Fix:** This is normal — the voice will work after you interact with the page (tap any button).

### Issue: Build fails on Vercel

**Cause:** Files in wrong location.

**Fix:** Make sure your repo structure is exactly:
- `index.html` (in root)
- `vercel.json` (in root)
- `api/chat.js` (inside api folder)

---

## How the cost works

Every time a user sends a message, you pay Anthropic about **$0.003** (less than half a cent).
Your $5 free credit gives you about **1,500 messages**.

For real users: most users won't hit the free credit limit during testing.

---

## Next Steps After This Works

Once the app is running, the path forward is:
1. **Test with friends** (5-10 people) → gather feedback
2. **Add login** with Supabase (free tier supports 50,000 users)
3. **Add payment** with Stripe (when ready to charge)
4. **Wrap as mobile app** with Capacitor (free, publishes to App Store/Play Store)

Total cost to reach the App Store: **$99 Apple + $25 Google = $124**.

That's it. You can do this without external developers.

---

## You've got this 💪

Take it one step at a time. If something breaks, send a screenshot of the exact error
in your next chat and you'll get a fix in minutes.
