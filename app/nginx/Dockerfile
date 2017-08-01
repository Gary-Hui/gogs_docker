FROM ubuntu:14.04

RUN apt-get update \
	&& apt-get -y install nginx \
	&& rm -rf /var/lib/apt/lists/* \
  	&& chown -R www-data:www-data /var/lib/nginx

COPY config/nginx/ /etc/nginx/

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80
EXPOSE 443
