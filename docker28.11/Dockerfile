FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Moscow
RUN apt update && apt install -y \
    default-jdk \
    maven \
    tomcat9 \
    git && \
    apt clean
WORKDIR /home/regina
RUN git clone https://github.com/geoserver/geoserver.git
WORKDIR /home/regina/geoserver
RUN mvn package
RUN cp target/geoserver.war /var/lib/tomcat9/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
