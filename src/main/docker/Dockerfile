FROM openjdk:8-jdk-alpine
VOLUME /tmp
CMD echo Doing copy: ${project.build.directory}/*.jar app.jar
COPY /home/davids/code/myproject/target/*.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]