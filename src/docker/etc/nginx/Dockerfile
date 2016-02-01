FROM nginx:latest

CMD ["pwd"]

RUN mkdir -p /etc/nginx/sites-available/ && mkdir -p /etc/nginx/sites-enabled/
RUN ln -s /etc/nginx/sites-available/symfony.conf /etc/nginx/sites-enabled/symfony
RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf
RUN usermod -u 1000 www-data

ADD nginx.conf /etc/nginx/
ADD symfony.conf /etc/nginx/sites-available/

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
