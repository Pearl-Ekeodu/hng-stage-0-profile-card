# HNG Internship - Stage 0: Profile Card

A beautiful, accessible, and fully-responsive profile card built with semantic HTML, modern CSS, and vanilla JavaScript.

**Live Demo**: [Your Live URL Here]  
**GitHub Repository**: [Your GitHub Repo URL]

---

## 📋 Table of Contents

- [Task Requirements Met](#task-requirements-met)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Deployment](#deployment)
- [Testing](#testing)
- [Project Structure](#project-structure)
- [Customization](#customization)
- [Browser Support](#browser-support)

---

## 🎯 Task Requirements Met

### ✅ All Required Elements with Correct data-testid Attributes

- **Profile card root container** - `data-testid="test-profile-card"`
- **Name** - `data-testid="test-user-name"`
- **Biography** - `data-testid="test-user-bio"`
- **Current time (milliseconds)** - `data-testid="test-user-time"`
- **Avatar image** - `data-testid="test-user-avatar"`
- **Social links list** - `data-testid="test-user-social-links"`
  - Twitter/X - `data-testid="test-user-social-twitter"`
  - GitHub - `data-testid="test-user-social-github"`
  - LinkedIn - `data-testid="test-user-social-linkedin"`
- **Hobbies list** - `data-testid="test-user-hobbies"`
- **Dislikes list** - `data-testid="test-user-dislikes"`

### ✅ Semantic HTML Structure

- `<article>` - Wraps the entire profile card
- `<header>` - Contains name and bio
- `<h1>` and `<h2>` - Proper heading hierarchy
- `<figure>` and `<figcaption>` - For avatar with caption
- `<nav>` - Social links navigation with `aria-label`
- `<section>` - Hobbies and dislikes sections with `aria-labelledby`
- `<time>` - Semantic time element for milliseconds
- `<ul>` and `<li>` - Lists for social links, hobbies, and dislikes

### ✅ Accessibility Features

- All interactive elements (links) are keyboard-focusable
- Visible focus states with high-contrast gold outline
- Semantic markup with ARIA labels where appropriate
- Image has descriptive `alt` attribute
- Proper heading structure for screen readers

### ✅ Responsive Design

- **Mobile** (< 768px): Single-column layout with stacked content
- **Tablet/Desktop** (≥ 768px): Two-column layout with avatar on left, content on right
- **Large Desktop** (≥ 1024px): Enhanced typography
- Flexbox and CSS Grid for flexible layouts
- Mobile-first approach

### ✅ Functionality

- **Time Display**: Shows current time in milliseconds using `Date.now()`
- **Live Updates**: Time updates every second automatically
- **Social Links**: All links open in new tab with `target="_blank"` and `rel="noopener noreferrer"`
- **Smooth Animations**: Card fade-in, hover effects on avatar and links

---

## ✨ Features

### Design & UI
- Modern dark gradient background with animated effects
- Glassmorphism card with animated gradient border
- Responsive layout (mobile, tablet, desktop)
- Professional typography using Google Fonts (Inter & Space Grotesk)
- Smooth animations and transitions
- Interactive hover effects on all elements

### Accessibility
- Full keyboard navigation support
- Visible focus states for all interactive elements
- ARIA labels for screen readers
- Semantic HTML structure
- Reduced motion support for accessibility preferences

### Performance
- Single HTML file with embedded CSS and JavaScript
- No external dependencies (except Google Fonts)
- Fast loading time
- Optimized animations using GPU acceleration

---

## 🛠 Technologies Used

- **HTML5** - Semantic markup
- **CSS3** - Modern styling (Grid, Flexbox, animations, gradients)
- **Vanilla JavaScript** - Time display functionality
- **Google Fonts** - Inter & Space Grotesk

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- No build tools or dependencies required!

### Running Locally

1. **Clone or Download the Repository**
   ```bash
   git clone <your-repo-url>
   cd <repository-name>
   ```

2. **Open the Project**
   
   **Option A: Direct Open**
   - Simply double-click `index.html` to open in your default browser
   
   **Option B: Local Server (Recommended)**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js http-server
   npx http-server
   ```
   Then navigate to `http://localhost:8000` in your browser

3. **That's it!** The profile card should display immediately with live time updates.

---

## 📁 Project Structure

```
project-root/
├── index.html          # Main HTML file with embedded CSS and JavaScript
└── README.md           # Documentation (this file)
```

**Note**: All CSS and JavaScript are embedded in `index.html` for simplicity.

---

## 🚀 Deployment

### Quick Deploy Options

#### Option 1: Netlify (Easiest)

**Drag & Drop Method:**
1. Go to [https://app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag your project folder onto the page
3. Get instant live URL!

**GitHub Method:**
1. Push code to GitHub
2. Go to [Netlify](https://app.netlify.com)
3. Click "Add new site" → "Import an existing project"
4. Connect GitHub and select your repository
5. Deploy!

#### Option 2: GitHub Pages

1. Push your code to GitHub
2. Go to repository Settings → Pages
3. Select "main" branch as source
4. Save and wait 2-3 minutes
5. Your site will be live at: `https://username.github.io/repo-name/`

#### Option 3: Vercel

1. Install Vercel CLI: `npm i -g vercel`
2. Run: `vercel`
3. Follow prompts
4. Get instant deployment!

---

## 🧪 Testing

### Manual Testing

1. Open `index.html` in your browser
2. Verify all elements are visible
3. Check that time updates every second
4. Test responsive layout (resize browser window)
5. Test keyboard navigation (Tab through links)
6. Verify hover effects work

### Automated Testing (Browser Console)

Open DevTools Console and run:

```javascript
// Verify all required data-testid attributes exist
const tests = {
  'Profile Card': document.querySelector('[data-testid="test-profile-card"]'),
  'User Name': document.querySelector('[data-testid="test-user-name"]'),
  'User Bio': document.querySelector('[data-testid="test-user-bio"]'),
  'User Time': document.querySelector('[data-testid="test-user-time"]'),
  'User Avatar': document.querySelector('[data-testid="test-user-avatar"]'),
  'Social Links': document.querySelector('[data-testid="test-user-social-links"]'),
  'Hobbies': document.querySelector('[data-testid="test-user-hobbies"]'),
  'Dislikes': document.querySelector('[data-testid="test-user-dislikes"]')
};

// Check results
Object.entries(tests).forEach(([name, element]) => {
  console.log(`${name}: ${element ? '✅ PASS' : '❌ FAIL'}`);
});
```

### Verify Time Display

```javascript
// Check time is displaying Date.now()
const timeElement = document.querySelector('[data-testid="test-user-time"]');
const displayedTime = parseInt(timeElement.textContent);
const currentTime = Date.now();
const difference = Math.abs(currentTime - displayedTime);

console.log('Time Test:', difference < 2000 ? '✅ PASS' : '❌ FAIL');
```

---

## 🎨 Customization

### Update Personal Information

Edit `index.html` to personalize your card:

1. **Your Name** (around line 716):
   ```html
   <h1 data-testid="test-user-name">Your Name</h1>
   ```

2. **Your Bio** (around line 717):
   ```html
   <p data-testid="test-user-bio">
       Your bio text here...
   </p>
   ```

3. **Your Avatar** (around line 705):
   ```html
   <img 
       data-testid="test-user-avatar" 
       src="YOUR_IMAGE_URL" 
       alt="Profile picture of Your Name"
   >
   ```
   **Tip**: Use [Unsplash](https://unsplash.com) or [UI Avatars](https://ui-avatars.com/) for profile images.

4. **Social Links** (around lines 732-758):
   ```html
   <a href="https://twitter.com/yourusername" ...>
   <a href="https://github.com/yourusername" ...>
   <a href="https://linkedin.com/in/yourprofile" ...>
   ```

5. **Hobbies & Dislikes** (around lines 768-786):
   - Update list items with your personal hobbies and dislikes

---

## 🌐 Browser Support

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

---

## 📋 Acceptance Criteria

- ✅ All required elements exist and are discoverable by data-testids
- ✅ HTML uses semantic tags (article, figure, nav, section, header, time)
- ✅ Time value displays `Date.now()` in milliseconds
- ✅ Avatar renders with descriptive alt attribute
- ✅ Social links have `target="_blank"` and `rel="noopener noreferrer"`
- ✅ Hobbies and dislikes are distinct lists
- ✅ Keyboard navigation works with visible focus styles
- ✅ Responsive layout at mobile/tablet/desktop breakpoints
- ✅ All interactive elements are keyboard-accessible

---

## 📤 Submission

**Submission Form**: [https://forms.gle/p7PcQ8nqVeH7rVcs9](https://forms.gle/p7PcQ8nqVeH7rVcs9)  
**Deadline**: October 19th, 2025

### What to Submit:
1. Live URL (Netlify, GitHub Pages, or Vercel)
2. GitHub repository link
3. Ensure README is clear and complete

---

## 👤 Author

**Pearl Ekeodu**  
Frontend Developer  
Building accessible and beautiful web experiences

---

## 📝 Additional Notes

- Built with vanilla HTML/CSS/JavaScript - no frameworks or build tools required
- Single-file architecture for easy deployment
- Time updates automatically every second using JavaScript
- All design decisions prioritize accessibility and user experience
- Fully responsive across all device sizes

---

## 🙏 Acknowledgments

Built for **HNG Internship Stage 0**  
Learn more about HNG: [https://hng.tech](https://hng.tech)

---

**License**: MIT  
**Version**: 1.0.0

---

Built with ❤️ for HNG Internship Stage 0

