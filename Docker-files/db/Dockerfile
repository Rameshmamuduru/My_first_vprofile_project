FROM mysql:8.0.33

LABEL project="My_first_vprofile_project"
LABEL maintainer="Ramesh Mamuduru"

# Set environment variables for MySQL
ENV MYSQL_ROOT_PASSWORD=vprodbpass
ENV MYSQL_DATABASE=accounts

ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql