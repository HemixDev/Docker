FROM maven:3.8.4-jdk-11-slim AS builder 

WORKDIR /app
COPY worker/pom.xml .
RUN mvn dependency:resolve
COPY worker/src /app/src

RUN mvn package

FROM openjdk:11-jre-slim

WORKDIR /app
COPY --from=builder /app/target/worker-jar-with-dependencies.jar .
CMD ["java", "-jar", "/app/worker-jar-with-dependencies.jar"]