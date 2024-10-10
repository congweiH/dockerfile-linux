FROM centos:8

# 备份原始文件
RUN mkdir -p /etc/yum.repos.d_backup
RUN mv /etc/yum.repos.d/ /etc/yum.repos.d_backup/

# 放入自定义配置
COPY ./repos/ /etc/yum.repos.d/

RUN yum clean all && yum makecache