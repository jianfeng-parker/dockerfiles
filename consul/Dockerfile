FROM centos:latest
MAINTAINER Parker Wu "programmingworld@163.com"
ENV REFRESHED_AT 2017-04-13

RUN yum -y install wget
RUN yum -y install unzip

ENV CONSUL_VERSION 0.8.0
ENV CONSUL_ARCHIVE consul_${CONSUL_VERSION}_linux_amd64.zip

RUN wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/${{CONSUL_ARCHIVE}
RUN unzip ${CONSUL_ARCHIVE}
RUN mv consul /usr/local/bin/
RUN chmod +x /usr/local/bin/consul
RUN rm ${CONSUL_ARCHIVE}
RUN consul version

ADD consul.json /config/

EXPOSE 53/udp 8300 8301 8301/udp 8302 8302/udp 8400 8500

VOLUME ["/data/consul"]

ENTRYPOINT [ "/usr/local/bin/consul" , "agent", "-config-dir=/config" ]
CMD []
