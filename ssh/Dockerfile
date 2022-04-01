FROM ubuntu:20.04
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
ENV SSH_USER matthieu

RUN apt-get update \
    && apt-get install -y openssh-server curl lftp

RUN mkdir /var/run/sshd
RUN mkdir /root/.ssh

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean

COPY start-container /usr/local/bin/start-container
RUN chmod +x /usr/local/bin/start-container

EXPOSE 22
ENTRYPOINT ["start-container"]
CMD ["/usr/sbin/sshd", "-D"]
