FROM docker.io/nginx:1.27-bookworm

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./app.conf.template /etc/nginx/templates/

RUN rm /etc/nginx/conf.d/*.conf
