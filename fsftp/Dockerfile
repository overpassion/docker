FROM	centos:7

MAINTAINER comghost

RUN	yum -y install vsftpd
RUN	mkdir /temp_cnf

COPY	user.sh /temp_cnf/user.sh
COPY	ftp.txt /temp_cnf/ftp.txt
COPY	vsftpd.conf /etc/vsftpd/vsftpd.conf
COPY	chroot_list /etc/vsftpd/chroot_list

VOLUME ["/home/ftpuser"]

RUN	sh /temp_cnf/user.sh

EXPOSE	20 21	50000-50010

CMD	["/usr/sbin/vsftpd","-obackground=NO"]
