# Use Ubuntu 24.04 as the base image
FROM ubuntu:24.04

# Update and install Nginx
RUN apt-get update && apt-get install -y nginx

# Copy the static HTML files into the Nginx directory
COPY index.html /var/www/html/index.html

# Expose the Nginx port
EXPOSE 80

# Command to run Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
