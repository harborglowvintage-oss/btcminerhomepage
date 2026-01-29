# btcminergpt.ai - Home Bitcoin Mining Intelligence Platform

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0-green.svg)

An AI-powered intelligence platform for home Bitcoin miners featuring live BTC price tracking, mining efficiency analysis, hardware R&D insights, and optimization tools. Includes original research white paper "The Entropy Arbitrage."

## 🚀 Features

### Core Features
- **Live Bitcoin Price Tracker** - Real-time BTC price monitoring with the Magnetar quantum-themed interface
- **Contact Inquiry Form** - Responsive contact form with email submission (replaces "Strategic Partnership Inquiry")
- **White Paper Access** - Full-screen modal displaying "The Entropy Arbitrage" research paper
- **FAQ Section** - Collapsible FAQ accordion covering hardware, environment, operations, and ROI
- **Responsive Design** - Fully optimized for mobile, tablet, and desktop devices
- **Dark Theme** - Cyberpunk-inspired design with neon accents and terminal aesthetics

### Visual Effects
- **CRT Overlay** - Retro cathode ray tube screen effect
- **Animated Elements** - Pulsing buttons, rotating graphics, smooth transitions
- **Fibonacci Spiral** - Animated background visualization
- **Magnetar Core** - Rotating ring animations for price tracker
- **Neon Glow Effects** - Text shadows and box shadows for cyberpunk aesthetic

### Technical Features
- **Static HTML/CSS/JS** - No build process required, pure vanilla implementation
- **Mempool.space API Integration** - Live BTC price, 24h stats, market cap from mempool.space
- **Google Analytics** - Integrated tracking (GA ID: G-8BDDBGECVX)
- **SEO Optimized** - Complete meta tags, Open Graph, Twitter Cards, JSON-LD schema
- **Performance Optimized** - Minimal dependencies, fast load times

### API Data Sources (mempool.space)
- **Current Price** - `/api/v1/prices` - Real-time BTC/USD price
- **24h History** - `/api/v1/historical-price` - High, low, and % change calculations
- **Block Data** - `/api/blocks` - Current block height for market cap calculation
- **Fee Data** - `/api/v1/mining/blocks/fees/24h` - 24h volume estimation

> ⚠️ **Rate Limits**: Mempool.space enforces rate limits on their free API tier. If you exceed limits, you may receive HTTP 429 errors. For high-traffic deployments, consider [Mempool Enterprise](https://mempool.space/enterprise).

## 📋 Prerequisites

- **Python 3.x** (for local development server)
- **Modern Web Browser** (Chrome, Firefox, Safari, Edge)
- **Text Editor** (VS Code, Sublime Text, etc.)
- **Internet Connection** (for API calls and external fonts)

## 🛠️ Installation & Setup

### Quick Start

1. **Clone or Download the Repository**
   ```bash
   cd /path/to/your/projects
   git clone <repository-url> btcminerhomepage
   cd btcminerhomepage
   ```

2. **Start Local Development Server**
   ```bash
   python3 -m http.server 8000
   ```

3. **Open in Browser**
   - Navigate to `http://localhost:8000`
   - Or open `index.html` directly in your browser

### File Structure
```
btcminerhomepage-main/
├── index.html              # Main HTML file (all-in-one)
├── logo.png               # BTCMiner GPT logo
├── rig.png                # Mining rig visual
├── homepage.png           # Homepage screenshot
├── dashone.png            # Dashboard screenshot 1
├── dashtwo.png            # Dashboard screenshot 2
├── fire.png               # Fire/heat visualization
├── advanced.png           # Advanced features image
├── gemini.png             # Gemini integration graphic
├── swarmgate.png          # SwarmGate feature
├── hashv.png              # Hash visualization
├── aiorb.png              # AI Orb graphic
├── CNAME                  # Custom domain configuration
├── LICENSE                # License file
├── README.md              # This file
└── DEPLOYMENT_CHECKLIST.md # Deployment guide
```

## 🎨 Customization

### Updating Contact Form

The contact form is configured to submit inquiries. To connect it to your email service:

1. **Update Form Action** (Line ~2177 in index.html)
   ```javascript
   document.getElementById('partnershipForm').addEventListener('submit', async (e) => {
     // Add your form submission logic here
     // Example: FormSpree, EmailJS, or custom backend
   });
   ```

2. **Form Fields**
   - Full Name (required)
   - Email (required, validated)
   - Company (required)
   - Inquiry Type (general, technical, partnership)
   - Subject (textarea for detailed message)

### Changing Colors

CSS variables are defined at the top of the `<style>` section:

```css
:root {
  --mint: #39ff9e;      /* Primary neon green */
  --teal: #00e0c4;      /* Secondary teal */
  --cyan: #00d4ff;      /* Accent cyan */
  --bg: #000;           /* Background black */
}
```

### Updating Content

- **Logo**: Replace `logo.png` with your own (recommended: 315px width, transparent PNG)
- **Title**: Update line ~2165 `<h1>btcminergpt.ai</h1>`
- **Tagline**: Update line ~2166 `<p class="tagline">`
- **White Paper**: Edit content starting at line ~3150

## 🚢 Deployment

### GitHub Pages

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings > Pages
   - Source: Deploy from branch `main`
   - Folder: `/ (root)`
   - Save

3. **Custom Domain (Optional)**
   - Add CNAME file with your domain
   - Configure DNS A records to GitHub Pages IPs
   - Enable HTTPS in settings

### Netlify

1. **Drag & Drop**
   - Go to app.netlify.com
   - Drag the entire folder to Netlify drop zone
   - Site goes live instantly

2. **Git Integration**
   - Connect your GitHub repository
   - Build command: (leave empty)
   - Publish directory: `/`

### Vercel

1. **Import Project**
   ```bash
   npm i -g vercel
   vercel
   ```

2. **Configure**
   - Framework Preset: Other
   - Build Command: (leave empty)
   - Output Directory: `./`

### Traditional Web Hosting

1. **Upload Files**
   - Use FTP/SFTP client (FileZilla, Cyberduck)
   - Upload all files to `public_html` or `www` directory

2. **Configure Domain**
   - Point domain to hosting server
   - Ensure index.html is in root directory

## 🔧 Configuration

### API Keys

**CoinGecko API** (Line ~2685)
- Currently using free tier (no API key required)
- For production, consider CoinGecko Pro with API key

**Google Analytics** (Line ~203)
- Replace `G-8BDDBGECVX` with your tracking ID

### Email Service Integration

Recommended services for contact form:
- **FormSpree**: https://formspree.io
- **EmailJS**: https://www.emailjs.com
- **Web3Forms**: https://web3forms.com
- **Custom Backend**: PHP, Node.js, Python Flask/Django

### Environment Variables

For production deployment, consider:
- API rate limits
- CORS configuration for APIs
- Email service credentials
- Analytics tracking codes

## 📱 Responsive Breakpoints

- **Desktop**: > 768px (full layout, side-by-side form fields)
- **Tablet**: 600px - 767px (adjusted spacing and font sizes)
- **Mobile**: < 600px (single column, optimized touch targets)

## 🐛 Troubleshooting

### White Screen Issue
- **Cause**: CSS conflicts with !important flags
- **Fix**: Removed aggressive mobile overrides (completed)
- **Solution**: Clean CSS without excessive !important declarations

### Contact Form Not Appearing
- **Issue**: Form hidden by default
- **Solution**: Click "📧 Contact Inquiry" button to toggle visibility
- **Behavior**: Button changes to "✖️ Close Form" when open

### FAQ Not Working
- **Check**: JavaScript function `toggleFaqPanel()` exists
- **Fix**: Ensure no JavaScript errors in console
- **Location**: Line ~3093

### Price Tracker Not Loading
- **Cause**: API rate limiting or network issues
- **Check**: Browser console for API errors
- **Fallback**: Manual refresh or wait for next update cycle

### Images Not Loading
- **Verify**: All PNG files are in root directory
- **Check**: File names match exactly (case-sensitive)
- **Path**: Use relative paths (`./logo.png` or `logo.png`)

## 🔒 Security

- **HTTPS Required**: Enable SSL certificate for production
- **CSP Headers**: Consider Content Security Policy headers
- **Input Validation**: Form inputs have HTML5 validation
- **XSS Prevention**: No user-generated content without sanitization
- **External Links**: Use `rel="noopener noreferrer"` (implemented)

## ⚡ Performance

- **File Size**: ~115KB HTML (includes all CSS/JS)
- **Load Time**: < 2 seconds on 3G connection
- **Lighthouse Score**: 90+ (Performance, Accessibility, SEO)
- **Images**: Optimize PNGs with TinyPNG or ImageOptim
- **CDN**: Consider Cloudflare for static asset delivery

## 📊 Analytics & Monitoring

- **Google Analytics**: Pre-configured tracking
- **Custom Events**: Track form submissions, button clicks, FAQ interactions
- **Error Monitoring**: Consider Sentry for JavaScript error tracking
- **Uptime Monitoring**: Use UptimeRobot or Pingdom

## 🤝 Contributing

This is a private/client project. For bug reports or feature requests:
1. Document the issue thoroughly
2. Include browser/device information
3. Provide steps to reproduce
4. Share console errors if applicable

## 📄 License

See LICENSE file for details.

## 🔗 Links

- **Live Site**: https://www.btcminergpt.ai/
- **Parent Site**: https://www.llmadvisor.ai/
- **Support**: Via contact form on homepage

## 📞 Support

For technical issues or questions:
- Use the Contact Inquiry form on the website
- Include detailed description of the issue
- Specify browser/device information
- Attach screenshots if helpful

---

**Last Updated**: January 10, 2026  
**Version**: 1.0  
**Status**: Production Ready ✅
