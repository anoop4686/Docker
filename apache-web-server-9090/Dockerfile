FROM ubuntu:22.04

# Name or email of person or group 
MAINTAINER "Anoop Maurya"

# Whon is writitng these file
LABEL name="Anoop Maurya"
LABEL email="Anoopmauray144@gmail.com"

# Installing recommanded package
# iputils : used for ping command
# net-tools, curl,  network-manager : networking command
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install net-tools vim curl network-manager iputils* vim -y

# Install apapche 
RUN apt-get install apache2 -y

# delete Exisiting docker configuration
RUN rm -rf /etc/apache2/sites-enabled/* && rm -rf /etc/apache2/sites-available/*

# Copy configuration and conf file
COPY learning /var/www/html
COPY web_server_configuration.conf /etc/apache2/sites-enabled/ 
COPY web_server_configuration.conf /etc/apache2/sites-available/

# copy for backup purpose.
COPY ./learning /root/backup-docker/learning/ 
COPY ./Dockerfile /root/backup-docker 
COPY ./web_server_configuration.conf /root/backup-docker

# open 8085 Ports
RUN echo "Listen 8085" >> /etc/apache2/ports.conf


# Expose is used for open port 80 and 8081
EXPOSE 9090

# ENTRYPOINT and CMD is used for exective apapche.
ENTRYPOINT [ "apache2ctl" ]
CMD ["-DFOREGROUND"]