# Pull base image
FROM centos:centos7

# Maintener
MAINTAINER James Barlow <james@dockerd.io>

# Install MongoDB
RUN rpm -vih http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
RUN yum update -y
RUN yum install redis -y
RUN yum clean all

# Copy config redis
ADD etc/redis.conf /etc/redis.conf

# User
USER root

# Mountable directories
VOLUME ["/var/lib/redis"]

# Set the environment variables
ENV HOME /var/lib/redis

# Working directory
WORKDIR /var/lib/redis

CMD ["/usr/bin/redis-server", "/etc/redis.conf"]

# Expose ports.
EXPOSE 6379
