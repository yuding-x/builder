FROM nginx:stable

# Copy static assets from GitHub Actions runner
COPY dist /usr/share/nginx/html

# Compress WASM files
RUN find /usr/share/nginx/html -name "*.wasm" -exec gzip -9 -k {} \;

# Copy custom NGINX configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start NGINX
CMD ["nginx", "-g", "daemon off;"]
