# Midlands Pressure Wash - Deployment Instructions

## 🚀 Quick Deploy to Netlify (5 minutes)

### Prerequisites
- GitHub account
- Netlify account (free - sign up at netlify.com)
- Your Anthropic API key

---

## Step-by-Step Deployment

### 1. Create GitHub Repository

1. Go to https://github.com/new
2. Name it: `midlands-pressure-wash`
3. Make it **Public** (or Private if you prefer)
4. Click "Create repository"

### 2. Upload Your Files to GitHub

**Option A: Via GitHub Web Interface (Easiest)**

1. Click "uploading an existing file" on your new repo page
2. Drag and drop these files:
   - `midlands-pressure-wash-fixed.html` (rename to `index.html`)
   - `netlify.toml`
   - The entire `netlify` folder (with the `functions` subfolder inside)

Your file structure should look like:
```
midlands-pressure-wash/
├── index.html
├── netlify.toml
└── netlify/
    └── functions/
        └── chat.js
```

3. Click "Commit changes"

**Option B: Via Git Command Line (If you're comfortable with Git)**

```bash
cd /path/to/your/files
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/midlands-pressure-wash.git
git push -u origin main
```

### 3. Deploy to Netlify

1. Go to https://app.netlify.com
2. Click "Add new site" → "Import an existing project"
3. Click "GitHub" and authorize Netlify
4. Select your `midlands-pressure-wash` repository
5. Click "Deploy site"

**Netlify will auto-detect your settings from netlify.toml!**

### 4. Add Your API Key (IMPORTANT!)

1. In Netlify, go to your site → "Site configuration" → "Environment variables"
2. Click "Add a variable"
3. Key: `ANTHROPIC_API_KEY`
4. Value: `YOUR_ACTUAL_API_KEY_HERE` (paste your Anthropic API key)
5. Click "Create variable"

### 5. Redeploy

1. Go to "Deploys" tab
2. Click "Trigger deploy" → "Clear cache and deploy site"
3. Wait 1-2 minutes for deployment

### 6. Test Your Site!

1. Click your Netlify URL (something like `https://sparkly-name-123456.netlify.app`)
2. Click the blue chat bubble
3. Type "Hey Splash, what do you do?"
4. Watch the AI magic happen! ✨

---

## 🔧 Troubleshooting

### Chatbot Shows Error Message

**Check these:**
1. API key is correctly set in Netlify environment variables
2. No spaces or quotes around the API key
3. API key starts with `sk-ant-api03-`
4. You clicked "Clear cache and deploy site" after adding the key

### Function Not Found

**Fix:**
1. Make sure `netlify/functions/chat.js` exists
2. Check that `netlify.toml` is in the root directory
3. Redeploy the site

### CORS Error

This means the function isn't working. Check:
1. Function deployed correctly (Netlify → Functions tab)
2. Environment variable is set
3. Try visiting `https://your-site.netlify.app/.netlify/functions/chat` - should return an error but NOT a 404

---

## 📝 Custom Domain (Optional)

Want to use a custom domain like `midlandspressurewash.com`?

1. Buy domain from Namecheap/GoDaddy/etc
2. In Netlify: Site configuration → Domain management → Add custom domain
3. Follow Netlify's DNS instructions
4. Done! SSL certificate automatically added

---

## 💰 Cost

**Total: $0/month** (until you hit limits)

Netlify Free Tier includes:
- 100GB bandwidth/month
- 300 build minutes/month
- 125,000 function requests/month

Anthropic API costs ~$3 per 1,000 conversations.

For a pressure washing business, expect $10-20/month max in API costs.

---

## 🔐 Security Notes

✅ API key is secure (stored in Netlify, never exposed to browser)
✅ CORS is properly configured
✅ HTTPS automatically enabled
✅ Functions are rate-limited by Netlify

---

## 🎯 What You Just Built

You now have:
- Production-grade website
- AI-powered chatbot (using Claude Sonnet 4)
- Secure backend proxy
- Auto-scaling infrastructure
- Free hosting + SSL certificate
- Custom domain ready

**This is the exact same architecture that million-dollar companies use.**

---

## Need Help?

If something isn't working:
1. Check Netlify function logs (Functions tab → click on chat function → View logs)
2. Check browser console (F12)
3. Verify API key in environment variables

---

## Next Steps

1. **Test thoroughly** - Try different questions with Splash
2. **Add client's photos** - Replace gallery placeholders
3. **Connect Google Reviews** - Add their review widget
4. **Add analytics** - Google Analytics or Plausible
5. **Build quote calculator** - Next phase of the project!

---

You're live! 🚀🎉
