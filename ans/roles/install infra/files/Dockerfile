# Базовый образ с nginx и php
FROM yiisoftware/yii2-php:8.1-fpm-nginx

# Добавляем наше веб приложение
ADD . /app

RUN chown www-data:www-data runtime web/assets
# Удаляем конфиги сайтов которые там есть
RUN rm -Rf /etc/nginx/sites-enabled/*

# Добавляем наш конфиг
ADD site.conf /etc/nginx/sites-available/site.conf
# Включаем его
RUN ln -s /etc/nginx/sites-available/site.conf /etc/nginx/sites-enabled/site.conf
