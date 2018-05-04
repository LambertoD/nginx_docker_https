FROM nginx
RUN rm /etc/nginx/conf.d/default.conf

RUN mkdir /etc/ssl/private && mkdir -p /etc/nginx/snippets

COPY files/certs/etc/ssl/private/nginx-selfsigned.key /etc/ssl/private/nginx-selfsigned.key
COPY files/certs/etc/ssl/certs/nginx-selfsigned.crt /etc/ssl/certs/nginx-selfsigned.crt
COPY files/certs/etc/ssl/certs/dhparam.pem /etc/ssl/certs/dhparam.pem
COPY files/certs/etc/nginx/snippets/*.conf /etc/nginx/snippets/

COPY files/nginx.conf /etc/nginx/nginx.conf
COPY files/index.html /usr/share/nginx/html

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log
