FROM alpine:3.18

RUN apk update && apk upgrade && apk add openssl nginx curl vim sudo

#COPY ./conf/nginx.conf /etc/nginx/sites-available/default

RUN mkdir -p /run/nginx

RUN mkdir -p /etc/nginx

COPY ./conf/nginx.conf /etc/nginx/nginx.conf
#COPY ./script/setup_ngnix.sh /setup_nginx


RUN	mkdir -p /etc/nginx/ssl && \
	openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes\
	-out /etc/nginx/ssl/certificate.crt \
	-keyout /etc/nginx/ssl/private.key \
	-subj "/C=CH/ST=Lausanne/L=Lausanne/O=42/OU=ngodard/CN=ngodard"

ENTRYPOINT ["nginx", "-g", "daemon off;"]
