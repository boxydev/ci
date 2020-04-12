FROM debian:buster-slim
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    gnupg2

RUN echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu bionic main" | tee -a /etc/apt/sources.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    ansible

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean
