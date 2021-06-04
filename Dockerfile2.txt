FROM centos:latest
MAINTAINER akhila
RUN yum install -y httpd zip unzip
ADD https://www.free-css.com/assets/files/free-css-templates/download/page267/jof.zip /var/www/html
WORKDIR /var/www/html
RUN unzip jof.zip
RUN cp -rvf jof/* .
RUN rm -rf jof.zip
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80