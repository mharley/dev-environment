FROM centos:7
MAINTAINER Amg Dev <amg-dev@athlonsports.com>

ARG NODE_VERSION

RUN curl --silent --location https://rpm.nodesource.com/setup_$NODE_VERSION | bash -
RUN yum -y install \
    vim \
    nodejs

RUN yum clean all

RUN npm install -g bower
RUN npm install -g gulp

CMD ["true"]
