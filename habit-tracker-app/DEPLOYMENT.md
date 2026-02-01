# 🚀 Habit Tracker - Deployment Guide

## 📁 Deployment Folder: `habit-tracker-app`

All production files are now in the `habit-tracker-app` folder, ready for deployment!

---

## 📦 What's Included

### HTML Files
- `index.html` - Main app (dashboard)
- `login.html` - Login page
- `profile.html` - Profile management

### CSS Files
- `styles.css` - Main styles
- `glass-spheres.css` - 3D glass sphere animations
- `stats-display.css` - Statistics display styles
- `emergency-fix.css` - Fix overrides
- `theme-panel.css` - Theme control panel

### JavaScript Files
- `app.js` - Main application logic
- `data.js` - Data management (user-specific storage)
- `user.js` - User profile system
- `streak.js` - Streak calculation
- `charts.js` - Heatmap charts
- `cursor-effects.js` - Cursor animations
- `glass-spheres.js` - Interactive 3D shapes

### Documentation
- `README.md` - Project overview
- `GOOGLE_SETUP.md` - Google OAuth setup guide

---

## 🌐 Deployment Options

### Option 1: Netlify (Recommended - FREE)

**Steps:**
1. Go to [Netlify](https://www.netlify.com/)
2. Sign up/Login
3. Drag & drop the `habit-tracker-app` folder to Netlify
4. Done! You get a URL like: `https://your-site.netlify.app`

**For Google Sign-In:**
- After deployment, update Google Cloud Console:
  - Add `https://your-site.netlify.app` to authorized origins
  - Add `https://your-site.netlify.app/login.html` to redirect URIs

---

### Option 2: Vercel (Also FREE)

**Steps:**
1. Go to [Vercel](https://vercel.com/)
2. Sign up/Login
3. Click "Add New" → "Project"
4. Upload the `habit-tracker-app` folder
5. Deploy! URL: `https://your-site.vercel.app`

**For Google Sign-In:**
- Same as Netlify - update authorized URLs in Google Cloud Console

---

### Option 3: GitHub Pages (FREE)

**Steps:**
1. Create a GitHub repository
2. Upload all files from `habit-tracker-app` folder
3. Go to Settings → Pages
4. Select branch: `main`, folder: `/` (root)
5. Save and wait for deployment
6. URL: `https://yourusername.github.io/repository-name`

**For Google Sign-In:**
- Update Google Cloud Console with your GitHub Pages URL

---

### Option 4: Firebase Hosting (FREE tier available)

**Steps:**
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login
firebase login

# Initialize
cd habit-tracker-app
firebase init hosting

# Choose options:
# - Select "Use an existing project" or create new
# - Public directory: . (current directory)
# - Single-page app: Yes
# - Set up GitHub Actions: No (optional)

# Deploy
firebase deploy
```

URL: `https://your-project.firebaseapp.com`

---

## ⚙️ Pre-Deployment Checklist

### 1. ✅ Update Google Client ID

In `login.html`, line 167:
```javascript
const GOOGLE_CLIENT_ID = 'YOUR_GOOGLE_CLIENT_ID_HERE';
```

Replace with your actual Client ID from Google Cloud Console.

### 2. ✅ Test Locally First

**Using VS Code Live Server:**
```
1. Open habit-tracker-app folder in VS Code
2. Right-click index.html
3. "Open with Live Server"
4. Test all features
```

**Or using Python:**
```bash
cd habit-tracker-app
python -m http.server 8080
# Open http://localhost:8080
```

**Or using Node.js:**
```bash
cd habit-tracker-app
npx http-server -p 8080
# Open http://localhost:8080
```

### 3. ✅ After Deployment

1. **Update Google OAuth Settings:**
   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Credentials → Your OAuth Client ID
   - Add production URLs:
     - Authorized JavaScript origins: `https://your-domain.com`
     - Authorized redirect URIs: `https://your-domain.com/login.html`

2. **Test Features:**
   - ✅ Login page loads
   - ✅ Google Sign-In works
   - ✅ Guest login works
   - ✅ Create habits
   - ✅ Check-in habits
   - ✅ View profile
   - ✅ Glass spheres animate
   - ✅ Theme panel works

---

## 🎨 Customization Before Deploy

### Change App Name/Branding
Edit in `index.html`, `login.html`, `profile.html`:
```html
<title>Your App Name - Habit Tracker</title>
<h1>Your App Name</h1>
```

### Change Theme Colors
Edit `styles.css` - CSS variables at the top:
```css
:root {
    --color-primary: #9333ea; /* Purple - change this */
    /* ... other colors */
}
```

### Change Default Glass Sphere Theme
Edit `glass-spheres.js`, line 12:
```javascript
colorTheme: 'purple', // Change to 'blue', 'rainbow', 'white'
```

---

## 📊 File Structure

```
habit-tracker-app/
├── index.html              # Main dashboard
├── login.html              # Login page
├── profile.html            # Profile management
├── styles.css              # Main styles
├── glass-spheres.css       # 3D animations
├── stats-display.css       # Stats styles
├── emergency-fix.css       # Style fixes
├── theme-panel.css         # Theme panel
├── app.js                  # Main app logic
├── data.js                 # Data storage
├── user.js                 # User profiles
├── streak.js               # Streak calculations
├── charts.js               # Charts/heatmaps
├── cursor-effects.js       # Cursor animations
├── glass-spheres.js        # 3D shapes
├── README.md               # Project info
└── GOOGLE_SETUP.md         # OAuth setup guide
```

---

## 🔒 Security Notes

**Before Going Public:**

1. **Don't commit sensitive data** - Client ID is OK to expose (it's a public identifier)
2. **Set up domain restrictions** in Google Cloud Console
3. **Enable HTTPS** - Most hosting platforms do this automatically
4. **Consider adding analytics** (Google Analytics, Plausible, etc.)

---

## 📱 Mobile Optimization

The app is already mobile-responsive! Features:
- ✅ Responsive design
- ✅ Touch-friendly buttons
- ✅ Optimized glass spheres for mobile
- ✅ Mobile navigation

---

## 🐛 Troubleshooting

**Google Sign-In not working after deploy:**
- Check authorized origins in Google Cloud Console
- Make sure you're using HTTPS (not HTTP)
- Verify Client ID in login.html is correct

**Glass spheres not showing:**
- Check browser console for errors (F12)
- Clear browser cache
- Make sure all CSS/JS files uploaded correctly

**Data not persisting:**
- Check localStorage is enabled in browser
- Make sure you're on HTTPS (localStorage works better)

---

## 🎉 You're Ready to Deploy!

**Recommended:** Start with Netlify for easiest deployment.

**Next Steps:**
1. Choose a hosting platform
2. Upload the `habit-tracker-app` folder
3. Get your deployment URL
4. Update Google OAuth settings
5. Test everything
6. Share with users! 🚀

---

## 💡 Post-Deployment Ideas

- Add custom domain
- Set up email notifications
- Add social sharing
- Create landing page
- Add user analytics
- Create mobile app (Progressive Web App)

---

**Questions? Check GOOGLE_SETUP.md for OAuth setup details!**

Good luck with your deployment! 🎊
