FROM		centos:7

MAINTAINER	comghost

RUN		yum install -y httpd
RUN		yum install -y net-tools
RUN		systemctl enable httpd

VOLUME ["/var/www/html", "/etc/httpd"]

ADD		index.html /var/www/html/

ENTRYPOINT	/usr/sbin/httpd -D FOREGROUND

EXPOSE		80
