FROM centos:centos7

MAINTAINER NeilCao <neil.cao@assaabloy.com>

RUN  yum install -y maven,git,openssh-server;yum clean all

RUN mkdir ~/.ssh
COPY ~/.ssh/id_rsa.pub /root/.ssh
COPY ~/.ssh/id_rsa /root/.ssh
RUN chmod 600 ~/.ssh/id_rsa*

WORKDIR /opt

RUN git clone git@github.com:sikateweiqi/spring-boot-helloworld.git

WORKDIR /opt/spring-boot-helloworld

RUN mvn clean

RUN mvn package

WORKDIR /opt/spring-boot-helloworld/target

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-hello-world-0.0.1-SNAPSHOT.jar"]
