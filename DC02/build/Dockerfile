#use maven image for build
FROM maven:3.8.7-eclipse-temurin-17 AS builder
WORKDIR /app
# copy pom.xml
COPY pom.xml /app/source/pom.xml
RUN rm -rf /app/source && \
    git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /app/source && \
    cd /app/source && \
    mvn clean package && \
    cp target/*.war /app/output

