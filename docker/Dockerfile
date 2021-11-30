FROM centos:centos7

MAINTAINER NeilCao <neil.cao@assaabloy.com>

ADD spring-boot-hello-world-0.0.1-SNAPSHOT.jar /opt

WORKDIR /opt

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-hello-world-0.0.1-SNAPSHOT.jar"]
