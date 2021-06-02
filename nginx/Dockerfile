FROM nginx:alpine

RUN adduser -S -G www-data www-data

ARG ROOT_FOLDER

ADD nginx.conf /etc/nginx/
ADD symfony.conf /etc/nginx/conf.d/default.conf
RUN sed -i "s/ROOT_FOLDER/${ROOT_FOLDER}/g" /etc/nginx/conf.d/default.conf
RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

EXPOSE 80

CMD ["nginx"]
