FROM openjdk:8-jdk-alpine
VOLUME /tmp
CMD echo Doing copy: ${project.build.directory}/*.jar app.jar
RUN mkdir -p /tmp/test
COPY ${project.build.directory}/* /tmp/test/
ENTRYPOINT ["java","-jar","/app.jar"]