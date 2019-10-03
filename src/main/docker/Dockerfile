FROM openjdk:8-jdk-alpine
VOLUME /tmp
COPY maven/*.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]