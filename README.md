# Flummie - Artisan Flower Candles Website

A beautiful, elegant showcase website for Flummie's handcrafted flower candles. Built with HTML, CSS, and vanilla JavaScript with internationalization support (English, French, Dutch) - ready to be integrated into Next.js or any other framework.

## Features

### 🌸 Beautiful Design
- **Elegant Floral Theme**: Soft pinks, roses, and cream colors
- **Animated Flower Decorations**: Floating flowers on borders and rotating flowers in hero section
- **Responsive Layout**: Works perfectly on all devices
- **Smooth Animations**: Scroll animations, transitions, and CSS-only flower animations
- **Professional Typography**: Serif fonts for elegance

### 🌍 Internationalization (i18n)
- **Multi-language Support**: English, French, and Dutch
- **Language Switcher**: Elegant buttons in navigation (EN/FR/NL)
- **LocalStorage Persistence**: Remembers user's language preference
- **Complete Translation**: All content translated including navigation, gallery items, and footer

### 🖼️ Interactive Gallery
- **Filterable Gallery**: Filter by candle types (All, Alya, Aza, Rumos, Pure, Custom crafts)
- **Lightbox Viewer**: Click to view images in full screen
- **Keyboard Navigation**: Arrow keys to navigate, ESC to close
- **Smooth Transitions**: Fade effects and animations
- **Real Product Categories**: Curated candle collections

### 📱 Sections
1. **Hero**: Full-screen introduction with rotating animated flowers
2. **Featured**: Three key benefits (Handcrafted, Unique Designs, Premium Quality)
3. **Gallery**: Filterable image gallery with 6 real candle photos
4. **About**: Story about Flummie and her artisan work
5. **Instagram**: Follow section with real Instagram link (@_flummie)
6. **Contact**: Email contact (artflumie@gmail.com) and custom orders info
7. **Footer**: Links and social media

### ⚡ JavaScript Features
- Mobile hamburger menu
- Gallery filtering
- Lightbox image viewer
- Smooth scroll navigation
- Scroll animations
- Lazy loading support
- **Internationalization system**: Dynamic language switching with nested translation keys

## File Structure

```
flummie/
├── index.html              # Main HTML file with data-i18n attributes
├── css/
│   └── styles.css          # All styling including animations
├── js/
│   ├── translations.js     # i18n translations (EN, FR, NL)
│   └── script.js           # Interactive functionality + i18n logic
├── images/                 # Real candle photos
│   ├── alya.PNG            # White Rose Bloom candle
│   ├── alya-2.jpg          # Pink Rose Bloom candle
│   ├── aza.jpg             # Aza Bouquet candle
│   ├── rumos.PNG           # Rumos deep red rose pot
│   ├── pure.PNG            # Pure mixed flower bouquet
│   ├── custom-gift-white-rose.jpg  # Custom white flower candle
│   ├── bg-flower.png       # Flower decoration for animations
│   └── flummie-logo.jpg    # About section logo
└── README.md               # This file
```

## How to Use

### 1. Images
All images are already in place:
- **Gallery**: 6 real candle photos organized by product category
- **Logo**: Flummie logo for about section
- **Decorations**: Animated flower background (bg-flower.png)

Recommended image sizes if adding more:
- Gallery images: 800x800px (square, 1:1 ratio)
- Logo/About image: 600x800px (portrait)
- Decoration: PNG with transparency

### 2. Contact Information
Current setup (configured in `index.html` and `translations.js`):
- **Email**: artflumie@gmail.com
- **Instagram**: @_flummie
- **Instagram URL**: https://www.instagram.com/_flummie?igsh=MWV3c2g2bXMyeHBybw==

### 3. Translations
Edit `js/translations.js` to modify or add languages:
```javascript
const translations = {
    en: { /* English translations */ },
    fr: { /* French translations */ },
    nl: { /* Dutch translations */ }
};
```

Each language object contains nested keys for:
- Navigation, Hero, Featured, Gallery, About, Instagram, Contact, Footer

### 4. Customize Content
- **HTML**: Add `data-i18n="section.key"` attributes to new elements
- **Translations**: Update corresponding keys in `translations.js`
- **Styles**: Modify CSS variables in `:root` for colors
- **Gallery**: Update filter categories and `data-category` attributes

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
Current categories:
- **All**: Shows all candles
- **Alya**: White and Pink Rose Bloom candles
- **Aza**: Elegant rose candle bouquet
- **Rumos**: Deep red rose pot
- **Pure**: Mixed flower pot bouquet
- **Custom crafts**: Custom white flower candles for events

To add/modify:
1. Update filter buttons in `index.html`
2. Add `data-category` to gallery items
3. Add translations in `translations.js` under `gallery.filters`

### Flower Animations
Two types of CSS-only animations:

1. **Border Floating Flowers**: 6 flowers positioned on page borders
   - Fade in/out with rotation and float movement
   - 8-10 second animation cycles with staggered delays
   - Hidden on mobile for cleaner experience

2. **Hero Rotating Flowers**: 2 large flowers in hero section
   - Full 360° rotation with scale transformations
   - 12-second cycles with 6-second offset
   - Drop shadows for better visibility

Both use `bg-flower.png` and are fully responsive.

## JavaScript Functions

### Internationalization (i18n)
```javascript
// Load and switch languages
function updateContent(lang) {
    // Updates all elements with data-i18n attributes
    // Saves preference to localStorage
}

// Language switcher buttons
document.querySelectorAll('.lang-btn').forEach(button => {
    button.addEventListener('click', () => {
        const lang = button.getAttribute('data-lang');
        updateContent(lang);
    });
});
```

### Gallery Filter
```javascript
// Filters gallery items by category
filterButtons.forEach(button => {
    button.addEventListener('click', () => {
        const filter = button.getAttribute('data-filter');
        // Shows/hides items based on data-category
    });
});
```

### Lightbox
```javascript
// Opens image in fullscreen viewer
galleryItems.forEach(item => {
    item.addEventListener('click', () => {
        // Displays full-size image with caption
        // Supports keyboard navigation (arrows, ESC)
    });
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
- **Optimized Animations**: CSS-only transforms for 60fps (no JavaScript animations)
- **Minimal JavaScript**: ~260 lines of vanilla JS (including i18n)
- **Fast Load Time**: No external dependencies
- **LocalStorage**: Language preference cached for instant switching

## SEO Ready

- Semantic HTML5 structure
- Meta descriptions
- Alt text for images
- Proper heading hierarchy
- Mobile-friendly
- Multi-language support for international SEO

## Accessibility

- Keyboard navigation support (lightbox, menus)
- ARIA labels where needed
- Focus states on interactive elements
- Screen reader friendly
- High contrast text and visible animations
- Language switcher for international users

## Current Status

✅ **Completed**:
1. Real candle photos uploaded and categorized
2. Email contact configured (artflumie@gmail.com)
3. Instagram linked (@_flummie)
4. Multi-language support (EN/FR/NL)
5. Animated flower decorations
6. Fully responsive design
7. Git repository initialized

## Integration Checklist

When integrating into Next.js:

- [ ] Create component structure (Hero, Gallery, About, etc.)
- [ ] Convert CSS to CSS Modules or styled-components
- [ ] Migrate i18n to next-i18next or next-intl
- [ ] Replace vanilla JS with React hooks (useState, useEffect)
- [ ] Set up image optimization (next/image)
- [ ] Configure environment variables for contact info
- [ ] Implement dynamic routes for language paths (/en, /fr, /nl)
- [ ] Add analytics tracking (Google Analytics, Plausible)
- [ ] Set up SEO with next-seo or built-in metadata
- [ ] Test responsiveness across devices
- [ ] Consider adding a contact form (React Hook Form + API route)

## Tips for Next.js Migration

1. **i18n**: Use `next-i18next` and migrate `translations.js` to JSON files
   ```javascript
   // locales/en/common.json, locales/fr/common.json, etc.
   ```

2. **Images**: Use `next/image` for automatic optimization
   ```jsx
   <Image src="/images/alya.PNG" width={800} height={800} alt="Alya Candle" />
   ```

3. **Animations**: Keep CSS animations as-is (they're already optimized)
   - Consider `framer-motion` for interactive animations if needed

4. **State**: Use Context API or Zustand for gallery filter state
   ```jsx
   const [activeFilter, setActiveFilter] = useState('all');
   ```

5. **Routing**: Use Next.js Link component
   ```jsx
   <Link href="#gallery" scroll={false}>Gallery</Link>
   ```

## Support

For questions or issues with the template, feel free to reach out!

## License

This template is created for Flummie Candles. Free to use and modify.

---

Made with ❤️ for Flummie's beautiful candle artistry
