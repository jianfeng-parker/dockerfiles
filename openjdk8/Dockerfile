FROM centos:latest
MAINTAINER Parker Wu "programmingworld@163.com"
ENV REFRESHED_AT 2017-04-08

RUN yum -y install java-1.8.0-openjdk && yum clean all
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0
ENV PATH "$PATH":/$JAVA_HOME:/bin:.:
RUN java -version

