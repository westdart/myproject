FROM openjdk:8-jdk-alpine
VOLUME /tmp
COPY ${project.build.directory}/*.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]