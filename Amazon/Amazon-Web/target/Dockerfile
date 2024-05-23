FROM tomcat:latest
RUN cp -r webapps.dist/* webapps
COPY ./Amazon.war /usr/local/tomcat/webapps/
EXPOSE 8080
ENTRYPOINT ["bin/catalina.sh","run"]
