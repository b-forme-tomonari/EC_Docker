FROM mysql:8.0.26
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=ec_sys
ENV MYSQL_USER=ec_java
ENV MYSQL_PASSWORD=ecjava
COPY conf.d/mysql.cnf /etc/mysql/conf.d/my.cnf
COPY sql/* /docker-entrypoint-initdb.d/
EXPOSE 3306