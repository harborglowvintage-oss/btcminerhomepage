# 🚀 QUICK START GUIDE - btcminergpt.ai

## For Immediate Local Testing

### 1. Start the Server
```bash
cd btcminerhomepage-main
python3 -m http.server 8000
```

### 2. Open in Browser
- Go to: **http://localhost:8000**
- Or: **http://127.0.0.1:8000**

### 3. Test Key Features
- ✓ Click "📧 Contact Inquiry" button
- ✓ Click "📄 WHITE PAPER" button  
- ✓ Click "❓ FAQ" button at bottom
- ✓ Check live BTC price updates
- ✓ Test on mobile (Chrome DevTools)

---

## For Deployment (Choose One)

### Option A: GitHub Pages (Easiest, Free)
```bash
cd "/home/hgv/Downloads/Repo Backups/btcminerhomepage-main"
git init
git add .
git commit -m "Deploy btcminergpt.ai"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/btcminergpt.git
git push -u origin main
```

Then: GitHub Settings > Pages > Source: main branch > Save

### Option B: Netlify (Instant Deploy)
```bash
# Install CLI
npm install -g netlify-cli

# Deploy
cd "/home/hgv/Downloads/Repo Backups/btcminerhomepage-main"
netlify deploy --prod
```

Or: Drag folder to https://app.netlify.com/drop

### Option C: Vercel
```bash
npm i -g vercel
cd "/home/hgv/Downloads/Repo Backups/btcminerhomepage-main"
vercel
```

---

## 📋 Before Deploying - IMPORTANT!

### 1. Configure Contact Form (Required)
Choose an email service and update line ~2612 in index.html:

**Option 1: FormSpree** (Easiest)
```html
<form action="https://formspree.io/f/YOUR-FORM-ID" method="POST">
```

**Option 2: Web3Forms**
```javascript
// Add API key to form submission
const response = await fetch('https://api.web3forms.com/submit', {
  method: 'POST',
  body: formData
});
```

### 2. Update Google Analytics (Optional)
Replace `G-8BDDBGECVX` with your tracking ID (line 203)

### 3. Custom Domain (Optional)
Update CNAME file with your domain name

---

## ✅ Quick Checklist

Before going live:
- [ ] Contact form configured and tested
- [ ] Google Analytics ID updated (if needed)
- [ ] Images optimized (optional, for faster loading)
- [ ] Custom domain configured (if using)
- [ ] Tested on Chrome, Firefox, Safari
- [ ] Tested on mobile devices
- [ ] All buttons work correctly
- [ ] FAQ accordion expands/collapses
- [ ] BTC price loads successfully (mempool.space API)

---

## 📡 API Information

### Data Source: mempool.space
All Bitcoin price and network data is sourced from [mempool.space](https://mempool.space):

| Data Point | Endpoint | Update Frequency |
|------------|----------|------------------|
| Current Price | `/api/v1/prices` | Every 30 seconds |
| 24h High/Low | `/api/v1/historical-price` | On page load |
| Market Cap | Calculated from block height | On page load |
| 24h Volume | `/api/v1/mining/blocks/fees/24h` | On page load |
| Block Height | `/api/blocks` | On page load |

### Rate Limits
- **Free Tier**: Suitable for most websites
- **Enterprise**: [mempool.space/enterprise](https://mempool.space/enterprise) for high-traffic sites
- **429 Errors**: If rate limited, the tracker will retry automatically with exponential backoff

---

## 🐛 Common Issues & Quick Fixes

### Issue: White screen on mobile
**Fix:** Already resolved! Just deploy as-is.

### Issue: Contact form not visible
**Solution:** Click the "📧 Contact Inquiry" button to toggle it.

### Issue: Images not loading
**Check:** All PNG files are in the same directory as index.html

### Issue: BTC price not updating
**Solution:** Check browser console for API errors. The site uses mempool.space API which has rate limits:
- Free tier: Sufficient for normal use
- If you see 429 errors, wait a few minutes or consider [Mempool Enterprise](https://mempool.space/enterprise)
- All price data (current, 24h high/low, market cap, volume) comes from mempool.space

---

## 📞 Need Help?

1. Check **README.md** for detailed documentation
2. Review **DEPLOYMENT_CHECKLIST.md** for step-by-step guides
3. Read **PROJECT_SUMMARY.md** for complete overview

---

## 🎉 You're Ready!

Your btcminergpt.ai website is:
✅ Fully functional
✅ Mobile responsive  
✅ SEO optimized
✅ Production ready

**Just deploy and go live!** 🚀
