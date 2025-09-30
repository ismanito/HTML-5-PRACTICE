# HTML5 + CSS3 + Docker Practical

A responsive, accessible 4-page static website built with modern CSS3 and served via Docker.

## Technologies Used

- HTML5 (semantic markup, accessibility features)
- CSS3 (Grid, Flexbox, Custom Properties, Media Queries)
- Docker (nginx:alpine)

## Features

- **Responsive Design**: Mobile-first approach with breakpoints at 480px, 768px, and 1024px
- **Dark Mode**: Automatic dark theme based on user preference
- **Accessibility**: WCAG AA compliant, skip links, proper focus states
- **Modern CSS**: CSS Grid, Flexbox, custom properties (CSS variables)
- **Performance**: Optimized images, minimal CSS footprint
- **Dockerized**: Containerized with nginx for easy deployment

## Design System

### Color Palette
- **Light Mode**: Clean whites and grays with blue accent
- **Dark Mode**: Dark grays with high contrast and blue accent
- **Accessibility**: All color combinations meet WCAG AA contrast requirements (4.5:1)

### Typography
- **System Font Stack**: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif
- **Modular Scale**: 1.25 ratio for harmonious type hierarchy
- **Line Height**: 1.6 for optimal readability

### Spacing Scale
- Consistent 8px base unit with multipliers (0.5rem, 1rem, 1.5rem, 2rem, 3rem)

### Components
- **Cards**: Subtle shadows, rounded corners, responsive padding
- **Tables**: Zebra striping, responsive overflow, clear headers
- **Media**: Responsive images and video with styled captions
- **Navigation**: Flexible layout that stacks on mobile

## Accessibility Features

- **Skip Links**: Visible on focus for keyboard navigation
- **Focus States**: High-contrast focus indicators on all interactive elements
- **Semantic HTML**: Proper heading hierarchy and landmark roles
- **Reduced Motion**: Respects user preferences for reduced motion
- **Screen Reader**: Optimized for assistive technologies

## Local Development

1. Clone the repository
2. Open `index.html` in a web browser
3. Or serve via Docker (see Docker Commands below)

## Docker Commands

Build the Docker image:
```bash
docker build -t ismahanabdi/html5-css3-site:lab2 .
```

Run the container locally:
```bash
docker run --rm -p 8080:80 ismahanabdi/html5-css3-site:lab2
```

Push to Docker Hub:
```bash
docker login
docker push ismahanabdi/html5-css3-site:lab2

# Optional: Tag as latest
docker tag ismahanabdi/html5-css3-site:lab2 ismahanabdi/html5-css3-site:latest
docker push ismahanabdi/html5-css3-site:latest
```

## File Structure

```
html5-practical/
├─ index.html           # Home page
├─ about.html          # About page
├─ media.html          # Media gallery
├─ extras.html         # Interactive elements & tables
├─ assets/
│  ├─ css/
│  │  └─ styles.css    # Main stylesheet
│  ├─ images/          # Image assets
│  ├─ audio/           # Audio files
│  ├─ video/           # Video files
│  └─ captions/        # Video captions
├─ Dockerfile          # Container configuration
├─ .dockerignore       # Docker ignore rules
└─ README.md           # This file
```

## Performance Notes

- **CSS Size**: Under 50KB for fast loading
- **Images**: Responsive with proper `<picture>` elements and modern formats
- **Fonts**: System fonts avoid FOIT/FOUT issues
- **Caching**: nginx serves with appropriate cache headers

## Browser Support

- Modern browsers supporting CSS Grid and Custom Properties
- Graceful degradation for older browsers
- Mobile browsers (iOS Safari, Chrome Mobile, etc.)

## Lighthouse Scores

- **Performance**: 90+
- **Accessibility**: 95+
- **Best Practices**: 95+
- **SEO**: 95+

