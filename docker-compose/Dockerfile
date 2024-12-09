FROM maven:latest as build
RUN apt update
RUN apt install git -y
WORKDIR /app
RUN git clone https://github.com/geoserver/geoserver.git
RUN cd /app/java-tomcat maven-example && mvn package

FROM tomcat:latest
COPY --from=builder /app/src/web/app/target/*.war ./