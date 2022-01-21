FROM mariadb:10.7.1

ENV MYSQL_ROOT_HOST=% \
  MYSQL_ROOT_PASSWORD=password \
  TZ=Asia/Tokyo

COPY ./my.cnf /etc/mysql/mariadb.cnf
RUN chmod 644 /etc/mysql/mariadb.cnf
RUN mkdir -p /var/lib/mysql-files