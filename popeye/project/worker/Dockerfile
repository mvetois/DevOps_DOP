FROM maven:3.5-jdk-8-alpine as builder

USER root
WORKDIR /builder
COPY pom.xml .
RUN mvn dependency:resolve
COPY src/ /builder/src/
RUN mvn package


FROM openjdk:8-jre-alpine

COPY --from=builder /builder/target/*jar-with-dependencies.jar /worker-jar-with-dependencies.jar

CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
