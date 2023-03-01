
FROM openjdk:11 as build

EXPOSE 8080
RUN apt-get -y update
RUN apt-get install -y git

RUN git clone https://github.com/barais/doodlestudent.git

WORKDIR doodlestudent/api

RUN ./mvnw clean package -Dquarkus.package.type=uber-jar
CMD ["java", "-jar", "target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]