FROM ubuntu:16.04

RUN apt-get update -y &&\
 DEBIAN_FRONTEND=noninteractive apt-get -y install python-apt apt-transport-https &&\
 rm -rf /var/lib/apt/lists/*

RUN rm /etc/apt/apt.conf.d/docker-clean
RUN mkdir /etc/ansible/
VOLUME /sys/fs/cgroup /run/lock /run /tmp
ENV container=docker
CMD ["/sbin/init"]
