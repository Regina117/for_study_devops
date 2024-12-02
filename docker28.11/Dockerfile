FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Moscow
RUN apt-get update && apt-get install -y \
    default-jdk \
    maven \
    tomcat9 \
    tzdata \
    git && \
    apt-get clean
WORKDIR /home/regina
RUN git clone https://github.com/geoserver/geoserver.git
WORKDIR /home/regina/geoserver/src
RUN mvn package -DskipTests
RUN cp target/geoserver.war /var/lib/tomcat9/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
