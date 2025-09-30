# HTML5 + CSS3 Practical with Docker

This project demonstrates modern HTML5 semantics, CSS3 styling, accessibility, and containerized deployment.

## Pages

- **index.html** — Welcome page with semantic structure, skip link, headings, quotes, time, abbr, code/kbd/samp elements.
- **about.html** — Project information with sections, lists, definition lists, and internal links.
- **media.html** — `<picture>` responsive images, audio, video with VTT captions, and embedded content.
- **extras.html** — Data tables (caption/thead/tbody/tfoot), `<details>`, `<dialog open>`, `<progress>`, `<meter>` elements.

## Design System

### Design Tokens
The site uses a comprehensive design token system with CSS custom properties:

**Colors:**
- Light mode: Clean whites and blues with accessible contrast ratios
- Dark mode: Dark slate backgrounds with bright text (auto-detected via `prefers-color-scheme`)
- Brand: `#2563eb` (blue) with `#059669` (green) accent
- All color combinations meet WCAG AA contrast requirements (4.5:1 minimum)

**Typography:**
- Font stack: System fonts (`system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif`)
- Modular scale: 1.25 ratio from 0.75rem to 2.25rem
- Mono font: `'SF Mono', Monaco, 'Cascadia Code', 'Roboto Mono', Consolas, 'Courier New'`

**Spacing:**
- Scale: 0.25rem to 4rem (4px to 64px) for consistent rhythm
- Based on 4px baseline grid

### Layout System
- **CSS Grid**: Main content area with optional sidebar on large screens (1024px+)
- **Flexbox**: Navigation, card layouts, and component-level layouts
- **Mobile-first**: Responsive breakpoints at 480px, 768px, 1024px, 1280px

### Component Library
- **Cards**: Elevated design with subtle shadows, hover effects, and brand accent borders
- **Tables**: Striped rows, sticky headers, responsive horizontal scroll
- **Interactive Elements**: Custom styling for `<details>`, `<dialog>`, `<progress>`, `<meter>`

## Accessibility Features

### Focus Management
- Visible skip link (hidden until focused)
- High-contrast focus indicators (2px blue outline with offset)
- Keyboard navigation support for all interactive elements

### Color Contrast
- All text meets WCAG AA standards (4.5:1 minimum)
- Dark mode automatically adapts contrast ratios
- Semantic color usage (success, warning, brand)

### Motion Preferences
- Respects `prefers-reduced-motion: reduce` by disabling animations
- Smooth scroll behavior (can be disabled by user preference)
- Subtle, purposeful animations that enhance rather than distract

### Screen Reader Support
- Semantic HTML structure maintained
- ARIA labels where appropriate
- Proper heading hierarchy (h1 → h2 → h3)
- Skip link for efficient navigation

## Performance

- **CSS Size**: ~15KB (well under 50KB target)
- **System Fonts**: No web font loading delays
- **Responsive Images**: `<picture>` element with multiple sources
- **Optimized Animations**: GPU-accelerated transforms only

## Docker Containerization

### Build Commands
```bash
# Build the image
docker build -t <your-dockerhub-username>/html5-css3-site:lab2 .

# Run locally on port 8080
docker run --rm -p 8080:80 <your-dockerhub-username>/html5-css3-site:lab2

# Push to registry
docker login
docker push <your-dockerhub-username>/html5-css3-site:lab2

# Tag as latest
docker tag <your-dockerhub-username>/html5-css3-site:lab2 <your-dockerhub-username>/html5-css3-site:latest
docker push <your-dockerhub-username>/html5-css3-site:latest
```

### Container Details
- **Base Image**: `nginx:alpine` (minimal footprint)
- **Web Root**: `/usr/share/nginx/html`
- **Health Check**: HTTP GET on port 80 every 30s
- **Port**: 80 (mapped to 8080 locally)

### Testing
After building and running:
1. Visit `http://localhost:8080`
2. Test all pages load correctly
3. Verify media files (images, audio, video) work
4. Check responsive design at different viewport sizes
5. Test accessibility with screen reader or browser tools

## Live Deployment

- **GitHub Pages**: [https://ismanito.github.io/HTML-5-PRACTICE/](https://ismanito.github.io/HTML-5-PRACTICE/)
- **Docker Registry**: [Docker Hub](https://hub.docker.com/r/YOUR-USERNAME/html5-css3-site)

## Lighthouse Scores
Target scores (with actual results after testing):
- **Accessibility**: ≥95
- **Performance**: ≥90
- **Best Practices**: ≥95
- **SEO**: ≥95

## Development Notes

### Browser Support
- Modern browsers with CSS Grid and Flexbox support
- Graceful degradation for older browsers
- Progressive enhancement approach

### Code Organization
```
/assets/css/styles.css
├── Design Tokens (CSS Variables)
├── Base Reset & Typography
├── Layout (Grid & Flexbox)
├── Components (Cards, Tables, etc.)
├── Utilities (Spacing, Text, etc.)
├── Responsive Breakpoints
└── Print Styles
```

## Author
**Ismahan**  
Email: ismahan5@usiu.ac.ke  
Department of Computing, USIU

---
*Last updated: September 30, 2025*
