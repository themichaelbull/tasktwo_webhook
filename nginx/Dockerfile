FROM nginx:latest
# Copy contents into image
COPY nginx/nginx.conf .
RUN nginx.conf /etc/nginx/nginx.conf 
# Expose the correct port
EXPOSE 5500
# Create an entrypoint
