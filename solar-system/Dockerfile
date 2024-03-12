# AtomyCloud - Solar System Container Image | solar-system:1.0
# IMAGE: Debian GNU/Linux + nginx/1.25.4 + Solar Sytem HTML Site
# docker run -d -p 8080:80 atomycloud/solar-system
FROM nginx

RUN rm -rf /usr/share/nginx/html/ && mkdir /usr/share/nginx/html/

COPY ./files /usr/share/nginx/html/
