FROM centos:latest
MAINTAINER Parker Wu "programmingworld@163.com"

ENV REFRESHED_AT 2017-04-08

# yum install openjdk
RUN yum -y install java-1.8.0-openjdk-devel 

ENV JAVA_HOME /usr/lib/jvm/java-1.8.0
ENV PATH "$PATH":/$JAVA_HOME/bin:.:

# install tomcat8
ENV TOMCAT_VERSION 8.5.13
ENV ARCHIVE apache-tomcat-${TOMCAT_VERSION}

ENV INSTALL_DIR /usr/local
ENV TOMCAT_HOME ${INSTALL_DIR}/tomcat8
ENV TOMCAT_DOWNLOAD_URL http://apache.fayea.com/tomcat/tomcat-8/v${TOMCAT_VERSION}/bin/${ARCHIVE}.tar.gz

RUN mkdir -p ${INSTALL_DIR}
RUN curl -o tomcat8.tar.gz -L ${TOMCAT_DOWNLOAD_URL}
RUN tar zxvf tomcat8.tar.gz -C ${INSTALL_DIR}
RUN mv ${INSTALL_DIR}/${ARCHIVE} ${TOMCAT_HOME}
RUN rm tomcat8.tar.gz && ls -la
RUN chmod a+x ${TOMCAT_HOME}/bin/catalina.sh

ENV DEPLOYMENT_DIR ${TOMCAT_HOME}/webapps/

EXPOSE 8080

CMD ["bash"]
