#use maven image for build
FROM maven:3.8.7-eclipse-temurin-17 AS builder
WORKDIR /build
# copy pom.xml
COPY pom.xml /build/source/pom.xml
#clone
RUN rm -rf /build/source && \
    git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /build/source
#build project
RUN cd /build/source && \
    mvn clean package && \
    mkdir -p /build/output && \
    cp target/*.war /build/output

