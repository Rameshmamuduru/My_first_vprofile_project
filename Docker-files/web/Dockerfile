FROM nginx

LABEL project="My_first_vprofile_project"
LABEL maintainer="Ramesh Mamuduru"

# Remove default Nginx web content
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/nginvproapp.conf