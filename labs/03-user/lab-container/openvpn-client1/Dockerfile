FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN apt-get install -y wget
RUN apt-get install -y curl

RUN apt-get install -y iproute2
RUN apt-get install -y netcat-openbsd
RUN apt-get install -y iputils-ping
RUN apt-get install -y bash-completion
RUN apt-get install -y iptables
RUN apt-get install -y ifupdown
RUN apt-get install -y net-tools
RUN apt-get install -y openvpn

RUN apt-get -y clean
RUN echo -e '10.10.10.50\topenvpn' > /etc/hosts

RUN rm -rf /var/lib/apt/lists/*

COPY ./run.sh /usr/local/bin/run.sh
COPY ./openvpn-client1.ovpn /root/
COPY ./ca.crt /root/
CMD ["run.sh"]

USER root
WORKDIR /root
