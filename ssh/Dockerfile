FROM ubuntu:18.04
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y openssh-server
RUN mkdir /var/run/sshd

RUN mkdir -p /root/.ssh

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod 755 /usr/local/bin/docker-entrypoint.sh
ENTRYPOINT ["docker-entrypoint.sh"]

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
