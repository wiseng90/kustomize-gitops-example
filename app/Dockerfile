FROM --platform=linux/arm64/v8 maven:3.6.1-jdk-8-alpine AS build

#COPY ./ ./

#RUN mvn -B package -f /app/pom.xml clean package

WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

FROM openjdk:8-jre-alpine3.9

COPY --from=build /app/target/spring-boot-0.0.1-SNAPSHOT.jar /usr/share/demo.jar

CMD ["java", "-jar", "/usr/share/demo.jar"]

