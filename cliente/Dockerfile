FROM debian:latest



RUN apt update -y
RUN apt upgrade -y

RUN apt install apache2 php php-json php-intl php-xml php-mbstring php-imap libapache2-mod-php php-curl wget unzip nano -y

RUN mkdir -p /var/www/html/rainloop
COPY rainloop-latest.zip /var/www/html/rainloop
RUN unzip /var/www/html/rainloop/rainloop-latest.zip -d /var/www/html/rainloop

RUN chown -R www-data:www-data /var/www/html/rainloop && \
    chmod -R 755 /var/www/html/rainloop

#RUN apt nano -y
#RUN ln -s /etc/squirrelmail/apache.conf /etc/apache2/conf-enable/squirrelmail.conf

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
#COPY client.sh /etc/init.d