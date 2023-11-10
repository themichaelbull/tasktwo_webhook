FROM nginx:latest
# Copy contents into image
COPY nginx.conf .
RUN cp nginx.conf /etc/nginx/nginx.conf 
# Expose the correct port
EXPOSE 5000
# Create an entrypoint
