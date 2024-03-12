# AtomyCloud - nginx! Alpine Container Image | atomycloud/nginx:1.1
# IMAGE: Alpine v3.19.1 + nginx/1.25.4
# docker run -d -p 8080:80 atomycloud/atomycloud/nginx:1.1
FROM atomycloud/base:alpine-v3.19.1

RUN apk update && apk add nginx --no-cache && \
    adduser -D -g 'www' www && \
    mkdir /www && chown -R www:www /var/lib/nginx && \
    chown -R www:www /www && \
    mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.orig && \
    apk add openrc --no-cache && \
    mkdir -p /run/openrc && \
    touch /run/openrc/softlevel && \
    rc-update add nginx default

COPY ./files /www
RUN mv ./www/nginx.conf /etc/nginx/

ENTRYPOINT ["/sbin/init"]
