FROM centos:7
RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install mariadb mariadb-server && \
    yum clean all
VOLUME ["/etc/mysql", "/var/lib/mysql"]
WORKDIR /data
CMD ["mysqld_safe"]
EXPOSE 3306
