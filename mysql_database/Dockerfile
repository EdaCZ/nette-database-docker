FROM mysql:8.0

ADD ./init.sql /docker-entrypoint-initdb.d

ENV MYSQL_DATABASE=my_db MYSQL_ROOT_PASSWORD=root

EXPOSE 3306
