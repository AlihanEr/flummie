# Flummie - Artisan Flower Candles Website

A beautiful, elegant showcase website for Flummie's handcrafted flower candles. Built with HTML, CSS, and vanilla JavaScript - ready to be integrated into Next.js or any other framework.

## Features

### 🌸 Beautiful Design
- **Elegant Floral Theme**: Soft pinks, roses, and cream colors
- **Responsive Layout**: Works perfectly on all devices
- **Smooth Animations**: Scroll animations and transitions
- **Professional Typography**: Serif fonts for elegance

### 🖼️ Interactive Gallery
- **Filterable Gallery**: Filter by flower types (Roses, Tulips, Peonies, Mixed)
- **Lightbox Viewer**: Click to view images in full screen
- **Keyboard Navigation**: Arrow keys to navigate, ESC to close
- **Smooth Transitions**: Fade effects and animations

### 📱 Sections
1. **Hero**: Full-screen introduction with brand name
2. **Featured**: Three key benefits with icons
3. **Gallery**: Filterable image gallery with 8 placeholder images
4. **About**: Story about Flummie and her work
5. **Instagram**: Follow section with Instagram link
6. **Contact**: Email contact and custom orders info
7. **Footer**: Links and social media

### ⚡ JavaScript Features
- Mobile hamburger menu
- Gallery filtering
- Lightbox image viewer
- Smooth scroll navigation
- Scroll animations
- Lazy loading support

## File Structure

```
Flummie-Candles/
├── index.html          # Main HTML file
├── css/
│   └── styles.css      # All styling
├── js/
│   └── script.js       # Interactive functionality
├── images/             # Image placeholders (add your photos here)
│   ├── candle-1.jpg
│   ├── candle-2.jpg
│   ├── candle-3.jpg
│   ├── candle-4.jpg
│   ├── candle-5.jpg
│   ├── candle-6.jpg
│   ├── candle-7.jpg
│   ├── candle-8.jpg
│   └── about-flummie.jpg
└── README.md           # This file
```

## How to Use

### 1. Add Your Images
Replace the placeholder images in the `images/` folder:
- `candle-1.jpg` through `candle-8.jpg`: Gallery images
- `about-flummie.jpg`: About section photo

Recommended image sizes:
- Gallery images: 800x800px (square, 1:1 ratio)
- About image: 600x800px (portrait)

### 2. Update Contact Information
In `index.html`, update:
- Email address: `flummie.candles@example.com`
- Instagram handle: `@flummie.candles`
- Instagram URL: Update the actual Instagram link

### 3. Customize Content
Edit `index.html` to update:
- Gallery item titles and descriptions
- About section text
- Featured section benefits
- Footer information

## Integration with Next.js

This website is built to be easily integrated into Next.js:

### Option 1: Convert to Next.js Components

1. **Create page structure**:
```jsx
// pages/index.js
import Head from 'next/head';
import Hero from '@/components/Hero';
import Gallery from '@/components/Gallery';
// ... other components

export default function Home() {
  return (
    <>
      <Head>
        <title>Flummie - Artisan Flower Candles</title>
      </Head>
      <Hero />
      <Gallery />
      {/* ... other sections */}
    </>
  );
}
```

2. **Split CSS**:
- Move CSS to component-level or use CSS Modules
- Or use Tailwind CSS/styled-components

3. **Convert JavaScript**:
- Use React hooks (useState, useEffect)
- Replace vanilla DOM manipulation with React state

### Option 2: Use as Static Pages

1. Copy files to Next.js `public/` folder
2. Access via `/candles.html` route
3. Gradually migrate to React components

## Customization Guide

### Colors
Edit CSS variables in `styles.css`:
```css
:root {
    --primary-color: #d4a5a5;    /* Main pink */
    --secondary-color: #9b7e7e;  /* Dark rose */
    --accent-color: #e8b4b8;     /* Light pink */
}
```

### Fonts
Currently uses:
- Headings: Georgia (serif)
- Body: Georgia (serif)

To change fonts, update the `font-family` in `styles.css`

### Gallery Categories
Add or modify categories in:
1. HTML filter buttons
2. Gallery items `data-category` attributes
3. JavaScript filter logic (automatically works)

## JavaScript Functions

### Gallery Filter
```javascript
// Filters gallery items by category
filterButtons.forEach(button => {
    button.addEventListener('click', () => {
        // Filter logic
    });
});
```

### Lightbox
```javascript
// Opens image in fullscreen viewer
galleryItems.forEach(item => {
    item.addEventListener('click', () => {
        // Open lightbox
    });
});
```

### Mobile Menu
```javascript
// Toggle mobile navigation
hamburger.addEventListener('click', () => {
    navMenu.classList.toggle('active');
});
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## Performance

- **Lazy Loading**: Images load as you scroll
- **Optimized Animations**: CSS transforms for 60fps
- **Minimal JavaScript**: Only ~200 lines of vanilla JS
- **Fast Load Time**: No external dependencies

## SEO Ready

- Semantic HTML5 structure
- Meta descriptions
- Alt text for images
- Proper heading hierarchy
- Mobile-friendly

## Accessibility

- Keyboard navigation support
- ARIA labels where needed
- Focus states on interactive elements
- Screen reader friendly
- High contrast text

## Next Steps

1. **Add Real Images**: Replace placeholders with actual candle photos
2. **Update Content**: Customize all text to match your brand
3. **Set Up Contact**: Configure email address
4. **Link Instagram**: Add real Instagram profile link
5. **Test on Mobile**: Ensure everything works on phones/tablets

## Integration Checklist

When integrating into Next.js:

- [ ] Create component structure
- [ ] Convert CSS to CSS Modules or styled-components
- [ ] Replace vanilla JS with React hooks
- [ ] Set up image optimization (next/image)
- [ ] Add dynamic routing if needed
- [ ] Configure environment variables for contact info
- [ ] Set up form handling for contact section
- [ ] Add analytics tracking
- [ ] Set up SEO with next-seo
- [ ] Test responsiveness

## Tips for Next.js Migration

1. **Images**: Use `next/image` for automatic optimization
2. **Animations**: Consider framer-motion for React-friendly animations
3. **Routing**: Use Next.js Link component for navigation
4. **State**: Use Context API or Zustand for gallery filter state
5. **Forms**: Use formspree.io or API routes for contact form

## Support

For questions or issues with the template, feel free to reach out!

## License

This template is created for Flummie Candles. Free to use and modify.

---

Made with ❤️ for Flummie's beautiful candle artistry
