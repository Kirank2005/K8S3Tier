# the first stage of our build will use a maven 3.6.1 parent image
FROM maven:3.6.1-jdk-8-alpine AS MAVEN_BUILD
 
# copy the pom and src code to the container
COPY ./ ./
 
# package our application code
RUN mvn clean package
 
# the second stage of our build will use open jdk 8 on alpine 3.9
FROM openjdk:10-jre-slim

RUN mkdir -p /opt/to-do-app/ 
 
# copy only the artifacts we need from the first stage and discard the rest
COPY --from=MAVEN_BUILD ./target/to-do-listEntity-app-0.0.1-SNAPSHOT.jar /opt/to-do-app/ 

WORKDIR /opt/to-do-app/

EXPOSE 8080
# set the startup command to execute the jar

CMD ["java", "-jar", "to-do-listEntity-app-0.0.1-SNAPSHOT.jar"]

