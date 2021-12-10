FROM nginx:1.18-alpine

RUN addgroup -g 1000 app \
 && adduser -G app -u 1000 -h /var/www -s /bin/bash -S app
RUN touch /var/run/nginx.pid
RUN mkdir /sock

RUN apk add --no-cache curl openssl

RUN mkdir /etc/nginx/certs

# ARG TARGETARCH
# RUN cd /usr/local/bin/ \
#   && curl -L https://github.com/FiloSottile/mkcert/releases/download/v1.4.3/mkcert-v1.4.3-linux-$TARGETARCH -o mkcert \
#   && chmod +x mkcert

COPY ./conf/nginx.conf /etc/nginx/
COPY ./conf/default.conf /etc/nginx/conf.d/

COPY ./certs/magento.test+1.pem /etc/nginx/certs/
COPY ./certs/magento.test+1-key.pem /etc/nginx/certs/

RUN mkdir -p /etc/nginx/html /var/www/html \
  && chown -R app:app /etc/nginx /var/www /var/cache/nginx /var/run/nginx.pid /sock

EXPOSE 8443

USER app:app

WORKDIR /var/www/html
