FROM maven:3.5-jdk-8-alpine AS builder
WORKDIR /worker
COPY . .
RUN mvn dependency:resolve && mvn package

FROM openjdk:8-jre-alpine
COPY --from=builder /worker/target/worker-jar-with-dependencies.jar ./worker-jar-with-dependencies.jar
CMD [ "java", "-jar", "worker-jar-with-dependencies.jar" ]