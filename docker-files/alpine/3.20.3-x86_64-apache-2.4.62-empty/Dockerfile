# AtomyCloud - Apache2! Alpine Container Image | atomycloud/alpine:3.20.3-x86_64-apache-2.4.62
# IMAGE: Alpine:3.20.3 + Apache:2.4.62
# docker run -d -p 8080:80 atomycloud/alpine:3.20.3-x86_64-apache-2.4.62-empty
FROM atomycloud/os:alpine-minirootfs-3.20.3-x86_64

RUN apk update && apk add apache2 --no-cache && \
    addgroup -g 111 www; adduser -u 111 -D -S -G www www && \
    mkdir -p www; chown www:www /www; chmod 1777 /www && \
    chown -R www:www /etc/apache2 && \
    apk add openrc --no-cache && \
    mkdir -p /run/openrc && \
    touch /run/openrc/softlevel && \
    rc-update add apache2 default && \
    sed -i 's|DocumentRoot "/var/www/localhost/htdocs"|DocumentRoot "/www"|' /etc/apache2/httpd.conf && \
    sed -i 's|<Directory "/var/www/localhost/htdocs">|<Directory "/www">|' /etc/apache2/httpd.conf

WORKDIR /www
EXPOSE 80
ENTRYPOINT ["/sbin/init"]
