# php Docker環境

# Requirement
* [docker](https://www.docker.com/)

# Install
Docker起動
```
docker-compose up -d --build
```

コンテナに入る
```
docker exec -it php sh
```

# Usage

## Nginx
http://localhost:8000/

## Mysql
ID:root
PW:rootpw

## phpmyadmin
http://localhost:18888
ID:root
PW:rootpw

## mailhog
http://localhost:8025/
smtp:1025

# Note

# Author
* [こぴぺたん](https://twitter.com/c_a_p_engineer)

# License
[MIT license](https://en.wikipedia.org/wiki/MIT_License).
