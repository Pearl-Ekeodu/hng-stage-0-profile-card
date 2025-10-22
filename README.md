# HNG Internship - Stage 0 & 1: Profile Card & Multi-Page Application
   
My submission for HNG Internship Stage 0 & 1. A responsive profile card (Stage 0) extended into a multi-page application (Stage 1) with contact form and about page, built with vanilla HTML, CSS, and JavaScript.

**Live Demo**: [https://hng-stage-0-profile-card-black.vercel.app/]  
**GitHub Repository**: [https://github.com/Pearl-Ekeodu/hng-stage-0-profile-card]

---

## 📋 Table of Contents

- [Task Requirements Met](#task-requirements-met)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)


---

## 🎯 Task Requirements Met

### ✅ Stage 0 - Profile Card Elements with Correct data-testid Attributes

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

### ✅ Stage 1 - Contact Us Page Elements

- **Contact page container** - `data-testid="test-contact-page"`
- **Form fields**:
  - Full Name - `data-testid="test-contact-name"`
  - Email - `data-testid="test-contact-email"`
  - Subject - `data-testid="test-contact-subject"`
  - Message - `data-testid="test-contact-message"`
- **Submit button** - `data-testid="test-contact-submit"`
- **Error messages** - `data-testid="test-contact-error-<field>"`
- **Success message** - `data-testid="test-contact-success"`

### ✅ Stage 1 - About Me Page Elements

- **About page container** - `data-testid="test-about-page"`
- **Content sections**:
  - Bio - `data-testid="test-about-bio"`
  - Goals - `data-testid="test-about-goals"`
  - Confidence areas - `data-testid="test-about-confidence"`
  - Future note - `data-testid="test-about-future-note"`
  - Extra thoughts - `data-testid="test-about-extra"`

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
- **Form Validation**: Contact form with email format and message length validation
- **Page Navigation**: Seamless navigation between Profile, About Me, and Contact pages

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
   
Simply double-click `index.html` to open in your default browser

3. **That's it!** The profile card should display immediately with live time updates.

---

## 📁 Project Structure

```
project-root/
├── index.html          # Main profile page with embedded CSS and JavaScript
├── about.html          # About Me page with reflective content
├── contact.html        # Contact Us page with form validation
├── src/                # Assets folder
│   └── WhatsApp Image 2024-06-12 at 00.22.52.jpeg  # Profile image
└── README.md           # Documentation (this file)
```

**Note**: All CSS and JavaScript are embedded in each HTML file for simplicity.


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



## 👤 Author

**Pearl Ekeodu**  
Frontend Developer  
Building accessible and beautiful web experiences

---

## 📝 Additional Notes

- Built with vanilla HTML/CSS/JavaScript - no frameworks or build tools required
- Multi-page architecture for easy navigation
- Time updates automatically every second using JavaScript
- All design decisions prioritize accessibility and user experience
- Fully responsive across all device sizes
- Form validation with real-time feedback
- Consistent design language across all pages

---

## 🆕 Stage 1 New Features

### Contact Us Page
- **Form Validation**: Email format validation and message length requirements
- **Accessibility**: Proper labels, ARIA attributes, and keyboard navigation
- **Success/Error Handling**: Real-time feedback for form submissions
- **Responsive Design**: Optimized for all device sizes

### About Me Page
- **Reflective Content**: Personal journey, goals, and aspirations
- **Semantic Structure**: Proper HTML5 semantic elements
- **Consistent Styling**: Matches the main profile design
- **Accessible Navigation**: Easy movement between pages

### Navigation System
- **Seamless Navigation**: Links between all three pages
- **Consistent Design**: Unified color scheme and typography
- **Mobile-Friendly**: Touch-friendly navigation on all devices

---

## 🙏 Acknowledgments

Built for **HNG Internship Stage 0 & 1**  
Learn more about HNG: [https://hng.tech](https://hng.tech)

Built with ❤️ for HNG Internship

