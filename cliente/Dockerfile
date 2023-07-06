FROM ubuntu:latest


RUN apt update -y
RUN apt upgrade -y

RUN apt install apache2 -y 
RUN apt install php -y
RUN apt install php-json -y
RUN apt install php-intl -y
RUN apt install php-xml -y
RUN apt install php-mbstring -y 
RUN apt install php-imap -y
RUN apt install nano -y

RUN mkdir -p /var/www/html/rainloop && \
    wget -qO- https://www.rainloop.net/repository/webmail/rainloop-community-latest.zip | \
    unzip -q -d /var/www/html/rainloop -

RUN chown -R www-data:www-data /var/www/html/rainloop && \
    chmod -R 755 /var/www/html/rainloop

#RUN apt nano -y
#RUN ln -s /etc/squirrelmail/apache.conf /etc/apache2/conf-enable/squirrelmail.conf

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
#COPY client.sh /etc/init.d