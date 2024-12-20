FROM ubuntu

# Name or email of person or group
MAINTAINER "Anoop Maurya"

# Whon is writitng these file
LABEL name="Anoop Maurya"
LABEL email="Anoopmauray144@gmail.com"

# Installing recommanded package
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install net-tools curl vim apache2 openssh-server bind9-utils apache2-utils tcl -y

# Copy HTML file to code
COPY maxant /var/www/html

# Backup File
RUN mkdir -p /root/docker-backup/maxant
COPY ./maxant /root/docker-backup/maxant
COPY ./Dockerfile /root/docker-backup
COPY ./Readme.md /root/docker-backup

# creating volume
VOLUME /var/www/html
VOLUME /etc/apache2/

# open 8080 Ports

RUN echo "Listen 9090" >> /etc/apache2/ports.conf

# Expose port
EXPOSE 9090

ENTRYPOINT [ "apache2ctl" ]
CMD ["-DFOREGROUND"]