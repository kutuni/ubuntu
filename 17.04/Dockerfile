FROM ubuntu:17.04

MAINTAINER kutuni

ENV DEBIAN_FRONTEND noninteractive

# Install packages
RUN apt-get update -y \
    && apt-get -y install software-properties-common vim net-tools mlocate unzip make net-tools telnet wget iputils-ping locales curl --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN echo "127.0.0.1	localhost" >/etc/hosts; \
    echo "* - nofile 65535" > /etc/security/limits.conf;  \
    echo "* - memlock unlimited" >> /etc/security/limits.conf;  \
    echo vm.max_map_count=262144 >> /etc/sysctl.conf;  \
    echo vm.swappiness=0 >> /etc/sysctl.conf; \
    echo net.ipv6.conf.all.disable_ipv6 = 1 >> /etc/sysctl.conf;  \
    echo net.ipv6.conf.default.disable_ipv6 = 1 >> /etc/sysctl.conf;  \
    echo net.ipv6.conf.lo.disable_ipv6 = 1 >> /etc/sysctl.conf ; \
    echo 'set +o history' >> /etc/profile

## Set LOCALE to UTF8
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen en_US.UTF-8 && \
    dpkg-reconfigure locales && \
    /usr/sbin/update-locale LANG=en_US.UTF-8
