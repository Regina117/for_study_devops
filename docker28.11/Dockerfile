FROM ubuntu
RUN apt update 
RUN git clone https://github.com/geoserver/geoserver.git
RUN mvn package
RUN cp geoserver.war /var/lib/tomcat9/webapps/
