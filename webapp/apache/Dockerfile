FROM centos:7
ADD . /html/
WORKDIR /var/www/html/
COPY html/index.html /var/www/html/
RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install httpd && \
    yum clean all
ADD run-httpd.sh /run-httpd.sh
RUN chmod -v +x /run-httpd.sh
CMD ["/run-httpd.sh"]
