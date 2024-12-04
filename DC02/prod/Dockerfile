FROM tomcat:10.1.13-jre17-temurin-jammy
#delete cash from tomcat
RUN rm -rf /usr/local/tomcat/webapps/*
#copy war file
WORKDIR /var/lib/tomcat/webapps
#copy war file
COPY ./output/*.war ./