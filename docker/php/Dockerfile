FROM php:7.2-fpm
COPY php.ini /user/local/etc/php/

# CentOSのパッケージのダウンロード
# RUNでコマンドが走る
RUN apt-get update \
&& apt-get install -y zlib1g-dev mariadb-client unzip \
&& docker-php-install zip pdo_mysql

# comoser関連のDockerfile

COPY --from=composer:latest /usr/local/bin /usr/local/composer

ENV COMPOSER_ALLOW_SUPERUSER 1

ENV COMPOSER_HOME /composer

ENV PATH $PATH:/composer/vendor/bin

# 作業ディレクトリ
WORKDIR /var/www
# laravelをインストール
RUN composer global require "laravel/require"
