FROM centos:centos7

MAINTAINER NeilCao <neil.cao@assaabloy.com>

RUN  yum install -y maven;yum clean all

WORKDIR /opt

COPY . ./

RUN ls -tl

WORKDIR /opt

RUN mvn clean

RUN mvn package

RUN cp /opt/spring-boot-helloworld/target/spring-boot-hello-world-0.0.1-SNAPSHOT.jar ./

RUN mvn clean

RUN  yum remove -y maven

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "spring-boot-hello-world-0.0.1-SNAPSHOT.jar"]