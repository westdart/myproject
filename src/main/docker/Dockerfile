FROM openjdk:8-jdk-alpine
VOLUME /tmp
CMD echo Doing copy: ../../../../../../*.jar app.jar
COPY ../*.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]