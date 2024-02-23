FROM maven:3.6.1-jdk-8-alpine AS MAVEN_BUILD

COPY ./ ./

RUN mvn -f ./app/pom.xml clean package

FROM openjdk:8-jre-alpine3.9

RUN cp /usr/src/app/target/spring-boot-0.0.1-SNAPSHOT.jar /usr/share/demo.jar

CMD ["java", "-jar", "/usr/share/demo.jar"]

