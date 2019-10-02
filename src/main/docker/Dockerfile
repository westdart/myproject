FROM openjdk:8-jdk-alpine
VOLUME /tmp
CMD echo Doing copy: ${project.build.directory}/*.jar app.jar
COPY ${project.build.directory}/*.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]