#This is my DOCKFILE for rockylinux 8.6.20227707 clean os;
#version 1
#by zhanglaotang

#BASE IMAGE
FROM rockylinux:8.6.20227707
#MAINTAINER
MAINTAINER SRE TEAM
#repos
RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' \
    -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.aliyun.com/rockylinux|g' \
    -i.bak \
    /etc/yum.repos.d/Rocky-*.repo  && \
    dnf makecache
ENV TZ=Asia/Shanghai \
        LANG=en_US.UTF-8 \
        LANGUAGE=zh_CN:zh \
        LC_ALL=zh_CN.UTF-8
RUN  dnf upgrade  -y && \
     dnf install -y epel-release && \
     dnf install -y telnet tar  rng-tools wget ansible  openssh-clients subversion telnet glibc-common git gcc gcc-c++   net-tools  unzip glibc-langpack-zh  langpacks-zh_CN && \
     yum clean all  && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
CMD ["bash"]
