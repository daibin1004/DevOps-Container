#This is my DOCKFILE for jdk17;
#version 1
#by zhanglaotang

#BASE IMAGE
FROM  daibin1004/rockylinux:8.6
#MAINTAINER
MAINTAINER SRE TEAM
ENV TZ=Asia/Shanghai 
WORKDIR /data
RUN wget https://aka.ms/download-jdk/microsoft-jdk-17.0.5-linux-x64.tar.gz && \
	tar  xf /data/microsoft-jdk-17.0.5-linux-x64.tar.gz && \
	rm -f microsoft-jdk-17.0.5-linux-x64.tar.gz && \
	yum install glibc-common fontconfig -y	
RUN groupadd  tomcat && useradd  --no-log-init   -g tomcat tomcat && \
    chown -R tomcat.tomcat /data/ 
USER tomcat	


ENV JAVA_HOME /data/jdk-17.0.5+8
ENV CLASSPATH .:$JAVA_HOME/lib
ENV PATH $PATH:$JAVA_HOME/bin
