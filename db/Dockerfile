FROM mariadb:10.4

ARG DOWNLOAD_LINK="https://downloadseramba.s3-eu-west-1.amazonaws.com/CommunityTGZ/latest.tgz"
# Name of the main directory inside the archive
ARG ERAMBA_DIR=eramba_community

# Configure mariadb following the Eramba's requirements
RUN sed -i '/^#sql_mode.* /s/.*/sql_mode=/' /etc/mysql/my.cnf && \
    sed -i '/^#max_allowed_packet /s/^;//' /etc/mysql/my.cnf && \
    sed -i 's/^\(max_allowed_packet\s*=\s*\).*$/\1128M/' /etc/mysql/my.cnf && \
    sed -i '/^\[mysqld\]/a innodb_lock_wait_timeout=200' /etc/mysql/my.cnf && \
    # Download the db scheme
    apt update && \
    DEBIAN_FRONTEND=noninteractive apt-get -yq install curl &&\
    mkdir /tmp_src && \
    curl -o eramba_latest.tgz ${DOWNLOAD_LINK} && \
    tar zxvf /eramba_latest.tgz -C /tmp_src && \
    cp /tmp_src/${ERAMBA_DIR}/app/Config/db_schema/c*.sql /docker-entrypoint-initdb.d && \
    rm -r /tmp_src /eramba_latest.tgz