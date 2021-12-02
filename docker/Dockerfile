FROM centos:centos7

MAINTAINER NeilCao <neil.cao@assaabloy.com>

RUN  yum install -y maven,git

ADD spring-boot-hello-world-0.0.1-SNAPSHOT.jar /opt

WORKDIR /opt

RUN git clone git@github.com:sikateweiqi/spring-boot-helloworld.git

WORKDIR /opt/spring-boot-helloworld

RUN mvn clean

RUN mvn package

WORKDIR /opt/spring-boot-helloworld/target

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-hello-world-0.0.1-SNAPSHOT.jar"]
