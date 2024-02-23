FROM maven:3.6.1-jdk-8-alpine AS MAVEN_BUILD

COPY ./ ./

RUN mvn -f ./app/pom.xml clean package

FROM openjdk:8-jre-alpine3.9

ARG JAR_FILE=target/spring-boot-docker-0.0.1-SNAPSHOT.jar

WORKDIR /opt/app

COPY ${JAR_FILE} /demo.jar

ENTRYPOINT ["java","-jar","/demo.jar"]

