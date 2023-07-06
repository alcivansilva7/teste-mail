FROM ubuntu:latest


RUN apt update -y
RUN apt upgrade -y

#RUN apt install postfix courier-pop courier-imap telnet nano -y
RUN apt install postfix nano -y

COPY main.cf /etc/postfix
COPY mail.sh /etc/init.d

RUN chmod 755 /etc/init.d/mail.sh

EXPOSE 25/tcp
EXPOSE 587/tcp
EXPOSE 110/tcp
EXPOSE 143/tcp

CMD [ "/etc/init.d/mail.sh" ]