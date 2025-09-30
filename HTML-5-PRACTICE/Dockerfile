# Use nginx alpine for minimal footprint
FROM nginx:alpine

# Copy all site files to nginx web root
COPY . /usr/share/nginx/html

# Health check to ensure nginx is serving content
HEALTHCHECK --interval=30s --timeout=3s \
  CMD wget -qO- http://localhost:80/ >/dev/null || exit 1

# Expose port 80
EXPOSE 80

# nginx alpine image already has CMD configured to start nginx
# No additional configuration needed for serving static HTML/CSS/media files