FROM nginx

COPY files/index.html /usr/share/nginx/html
COPY files/nginx.conf /etc/nginx/sites-available/default

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log
