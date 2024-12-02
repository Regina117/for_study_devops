FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Moscow
RUN apt-get update && apt-get install -y \
    default-jdk \
    maven \
    tzdata \
    wget \
    git && \
    apt-get clean
RUN wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.97/bin/apache-tomcat-9.0.97.tar.gz && \
    tar xzf apache-tomcat-9.0.97.tar.gz -C /opt && \
    ln -s /opt/apache-tomcat-9.0.97 /opt/tomcat9
ENV MAVEN_OPTS="-Xmx2g -XX:MaxPermSize=512m"
WORKDIR /home/regina
RUN git clone https://github.com/geoserver/geoserver.git
WORKDIR /home/regina/geoserver/src
RUN mvn package -DskipTests
RUN cp /home/regina/geoserver/src/web/app/target/geoserver.war /opt/tomcat9/webapps/
EXPOSE 8080
ENTRYPOINT ["/opt/tomcat9/bin/catalina.sh"]
CMD ["run"]
