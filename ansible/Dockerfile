FROM debian:buster-slim
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    ansible

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean
