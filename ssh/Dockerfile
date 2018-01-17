FROM centos:latest

MAINTAINER SEIYA TSUKADA

ARG PASSWORD

RUN yum -y update
RUN yum -y install openssh-server passwd
RUN yum -y install gcc-c++ wget make

RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config
RUN sed -ri 's/#UsePAM no/UsePAM no/g' /etc/ssh/sshd_config

RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N ""
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_dsa_key -N ""

RUN echo "root:${PASSWORD}" | chpasswd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
