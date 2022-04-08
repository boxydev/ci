FROM debian:buster-slim
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y gnupg2 \
    && echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu bionic main" | tee -a /etc/apt/sources.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367 \
    && apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y ansible \
    && rm -rf /var/lib/apt/lists/*
