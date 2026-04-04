# CBT Training Program Landing Page

A professional, responsive landing page for the Cognitive Behavioral Therapy (CBT) training program in collaboration with Beck Institute and Source for Help (مورد مساعدة).

## Project Overview

This landing page showcases a comprehensive CBT training program led by Dr. Allen Miller, the Executive Director of Beck Institute. The program is designed for psychologists and mental health professionals seeking to establish a strong foundation in Cognitive Behavioral Therapy.

## Features

- **Responsive Design**: Fully responsive layout that works seamlessly on desktop, tablet, and mobile devices
- **Bilingual Support**: Arabic (RTL) and English language support
- **Professional Styling**: Modern, clean design with smooth animations and transitions
- **Accessibility**: WCAG compliant with keyboard navigation and focus management
- **Performance Optimized**: Fast loading times with optimized assets and lazy loading
- **SEO Ready**: Proper meta tags and semantic HTML structure
- **Netlify Ready**: Pre-configured for easy deployment on Netlify

## Project Structure

```
cbt-landing-page/
├── index.html          # Main HTML file
├── styles.css          # CSS styling
├── script.js           # JavaScript functionality
├── netlify.toml        # Netlify configuration
├── README.md           # This file
└── assets/
    ├── ad.jpg          # Event poster image
    ├── allen.jpg       # Dr. Allen Miller photo
    ├── beck.png        # Beck Institute logo
    └── logo.png        # Source for Help logo
```

## File Descriptions

### index.html
The main HTML file containing the complete landing page structure with:
- Navigation header with sticky positioning
- Hero section with call-to-action buttons
- About section with instructor information
- Program overview with two modules
- Detailed program information (dates, times, fees)
- Partnership section
- Call-to-action section
- Footer with links and information

### styles.css
Comprehensive CSS styling featuring:
- CSS variables for consistent theming
- Responsive grid layouts
- Smooth animations and transitions
- Mobile-first responsive design
- Professional color scheme (primary: #0099cc, accent: #f77f00)
- Hover effects and interactive elements

### script.js
JavaScript functionality including:
- Smooth scrolling for navigation links
- Intersection Observer for fade-in animations
- Sticky header effects
- Mobile menu support
- Scroll-to-top button
- Lazy loading for images
- Accessibility enhancements
- Performance monitoring

### netlify.toml
Netlify deployment configuration with:
- Build settings
- Cache control headers
- Security headers
- Redirect rules

## Deployment Instructions

### Option 1: Deploy to Netlify (Recommended)

1. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Click "New site from Git"
   - Connect your GitHub repository

2. **Configure Build Settings:**
   - Build command: Leave empty (static site)
   - Publish directory: `.` (root directory)
   - The `netlify.toml` file will handle the rest

3. **Deploy:**
   - Push changes to your repository
   - Netlify will automatically deploy

### Option 2: Manual Deployment to Netlify

1. **Drag and Drop:**
   - Go to [netlify.com/drop](https://netlify.com/drop)
   - Drag the entire project folder
   - Your site will be live in seconds

2. **Using Netlify CLI:**
   ```bash
   npm install -g netlify-cli
   netlify deploy --prod --dir=.
   ```

### Option 3: Deploy to Other Platforms

The static nature of this site means it can be deployed to:
- GitHub Pages
- Vercel
- AWS S3 + CloudFront
- Any static hosting service

Simply upload all files to your hosting provider.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Customization

### Colors
Edit the CSS variables in `styles.css`:
```css
:root {
    --primary-color: #0099cc;
    --secondary-color: #00b4d8;
    --accent-color: #f77f00;
    /* ... other variables ... */
}
```

### Content
Edit the text content directly in `index.html`. All content is clearly labeled with comments.

### Images
Replace images in the `assets/` folder:
- `allen.jpg` - Instructor photo
- `beck.png` - Beck Institute logo
- `logo.png` - Source for Help logo
- `ad.jpg` - Event poster

### Fonts
The page uses Google Fonts (Cairo and Poppins). To change fonts, modify the font import in `index.html` and update the CSS variables.

## Performance Optimization

The landing page includes several performance optimizations:
- Minified CSS and JavaScript
- Optimized images
- Lazy loading for images
- Efficient caching headers
- Minimal external dependencies

## Accessibility Features

- Semantic HTML structure
- ARIA labels where appropriate
- Keyboard navigation support
- Focus management
- Color contrast compliance
- Responsive text sizing

## SEO Optimization

- Descriptive meta tags
- Semantic HTML elements
- Proper heading hierarchy
- Alt text for images
- Mobile-friendly design
- Fast loading times

## Contact & Support

For questions or support regarding the landing page:
- Visit: [Source for Help](https://sourceforhelp.org)
- Registration Form: [https://forms.gle/drFoGezmd1qc7WQZ8](https://forms.gle/drFoGezmd1qc7WQZ8)

## Program Details

**Program Name:** CBT Fundamentals + CBT for Depression

**Instructor:** Dr. Allen Miller, Executive Director, Beck Institute

**Dates:** April 17-20, 2026

**Time:** 9 AM - 5 PM (Cairo Time)

**Format:** Online or In-Person

**Language:** Arabic interpretation available

**Registration Deadline:** February 10, 2026

**Fee:** $500-750 USD (depending on country)

## License

This landing page is created for the CBT Training Program in collaboration with Beck Institute and Source for Help.

## Version History

- **v1.0** (January 2026) - Initial release with complete landing page
  - Responsive design
  - Arabic/English support
  - Professional styling
  - Netlify configuration

---

**Last Updated:** January 24, 2026

**Created by:** Professional Web Design Team

For the latest updates and information, visit the registration form or contact Source for Help.
