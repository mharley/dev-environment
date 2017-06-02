FROM nginx:latest
MAINTAINER Amg Dev <amg-dev@athlonsports.com>

ADD nginx.conf /etc/nginx/
ADD default.conf/ /etc/nginx/conf.d
ADD upstream.conf/ /etc/nginx/conf.d
ADD sites-enabled/ /etc/nginx/sites-enabled

WORKDIR /etc/nginx

CMD ["nginx"]
