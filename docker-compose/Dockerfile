FROM maven:latest as build
RUN apt update
RUN apt install git -y
WORKDIR /app
RUN git clone https://github.com/geoserver/geoserver.git
WORKDIR /app/geoserver/src
RUN mvn package

FROM tomcat:latest
COPY --from=build /app/geoserver/src/target/*.war /usr/local/tomcat/webapps