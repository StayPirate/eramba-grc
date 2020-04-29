FROM mariadb:10.4

ARG DB_SCHEMA=e2.12.0.sql

COPY ${DB_SCHEMA} /docker-entrypoint-initdb.d

# Configure mariadb following the Eramba's requirements
RUN sed -i '/^#sql_mode.* /s/.*/sql_mode=/' /etc/mysql/my.cnf && \
    sed -i '/^#max_allowed_packet /s/^;//' /etc/mysql/my.cnf && \
    sed -i 's/^\(max_allowed_packet\s*=\s*\).*$/\1128M/' /etc/mysql/my.cnf && \
    sed -i '/^\[mysqld\]/a innodb_lock_wait_timeout=200' /etc/mysql/my.cnf