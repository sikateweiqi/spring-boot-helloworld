FROM centos:centos7

MAINTAINER NeilCao <neil.cao@assaabloy.com>

RUN mkdir ~/.ssh
RUN touch ~/.ssh/known_hosts
RUN ssh-keyscan -t rsa github.com > ~/.ssh/known_hosts
COPY ~/.ssh/id_rsa.pub ~/.ssh
COPY ~/.ssh/id_rsa ~/.ssh
RUN chmod 600 ~/.ssh/id_rsa*

RUN  yum install -y maven,git

WORKDIR /opt

RUN git clone git@github.com:sikateweiqi/spring-boot-helloworld.git

WORKDIR /opt/spring-boot-helloworld

RUN mvn clean

RUN mvn package

WORKDIR /opt/spring-boot-helloworld/target

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-hello-world-0.0.1-SNAPSHOT.jar"]
