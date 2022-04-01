FROM ubuntu:20.04
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
ENV FTP_USER matthieu
ENV FTP_PASSWORD password

RUN apt-get update \
    && apt-get install -y proftpd-basic whois

COPY proftpd.conf /etc/proftpd/conf.d/proftpd.conf

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean

COPY start-container /usr/local/bin/start-container
RUN chmod +x /usr/local/bin/start-container

EXPOSE 21
ENTRYPOINT ["start-container"]
CMD ["/usr/sbin/proftpd", "-n"]
