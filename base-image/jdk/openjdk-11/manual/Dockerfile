FROM centos:8

# 配置yum
RUN mkdir -p /etc/yum.repos.d_backup
RUN mv /etc/yum.repos.d/ /etc/yum.repos.d_backup/

COPY ./repos/ /etc/yum.repos.d/

RUN yum clean all && yum makecache

# 安装wget
RUN yum install -y wget

# 下载jdk11到 /tmp 目录，并重命名压缩包名称为jdk-11.tar.gz
RUN wget -O /tmp/jdk-11.tar.gz  https://download.java.net/openjdk/jdk11/ri/openjdk-11+28_linux-x64_bin.tar.gz

# 解压到 /opt 目录
RUN tar -xvf /tmp/jdk-11.tar.gz -C /opt/

ENV JAVA_HOME=/opt/jdk-11
ENV PATH=$PATH:$JAVA_HOME/bin

# 如果这条命令没有报错，说明java安装成功
RUN java -version