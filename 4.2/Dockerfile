FROM maven:3.5-jdk-8 as maven

COPY pom.xml /src/pom.xml

WORKDIR /src

RUN mvn dependency:go-offline -B

COPY . /src/

RUN mvn package

FROM openjdk:8u171-jre-alpine

WORKDIR /app

COPY --from=maven target/*.jar ./

# set the startup command to run your binary
CMD ["java", "-jar", "./app/spring-petclinic-2.2.0.BUILD-SNAPSHOT.jar"]



