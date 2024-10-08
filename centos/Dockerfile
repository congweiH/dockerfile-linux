FROM centos:8

COPY ./repos/ /etc/yum.repos.d/
RUN rm -rf /etc/yum.repos.d/CentOS-Linux-Extras.repo 

RUN yum clean all && yum makecache