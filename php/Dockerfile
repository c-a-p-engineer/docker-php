FROM php:8.0.1-fpm-alpine3.12

RUN apk update && \
    apk add --update --no-cache \
     shadow \
     bash && \
    docker-php-ext-install pdo_mysql

RUN apk add autoconf build-base && \
    pecl install xdebug && \
    docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# node のインストール npm のため
RUN apk add --update nodejs nodejs-npm

ARG PUID=1000
ARG PGID=1000
ARG USER_NAME="user"

ENV PUID ${PUID}
ENV PGID ${PGID}

# linuxコマンドを参照すること
# 新規グループを作成する
RUN groupadd -g ${PGID} ${USER_NAME}
# 新規ユーザーを作成し、グループに入れ、ユーザーのHomeディレクトリが無ければ作成する
RUN useradd -u ${PUID} -g ${USER_NAME} -m ${USER_NAME}
# ユーザーのパスワードとシェルを指定
RUN usermod -p "*" ${USER_NAME} -s /bin/sh

WORKDIR /var/www/app
