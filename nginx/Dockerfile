# Download nginx Docker Image
FROM nginx  

# Copy our default.conf into nginex Docker image overwriting the existing one.
# For a production version, you can copy a seperate "default.conf" file that does not have the "location" code:
#  location /sockjs-node {
#    proxy_pass http://client;
#    proxy_http_version 1.1;
#    proxy_set_header Upgrade $http_upgrade;
#    proxy_set_header Connection "Upgrade";
#  }
# make a new file like "prod.conf".
# and change the copy command to be:
# COPY ./default.conf /etc/nginx/conf.d/prod.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf