FROM nginx
WORKDIR /usr/share/nginx/html
COPY files/index.html index.html
## COPY files/nginx.conf /etc/nginx/nginx.conf

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log
