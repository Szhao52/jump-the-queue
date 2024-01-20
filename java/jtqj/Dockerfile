FROM maven:3.9.1-eclipse-temurin-11 AS build-step
WORKDIR /app
COPY . .
RUN mvn clean install
 
FROM eclipse-temurin:11-jdk-alpine AS production-step
COPY --from=build-step /app/server/target/jtqj-server-bootified.war .

EXPOSE 8081
ENTRYPOINT ["java", "-jar", "jtqj-server-bootified.war"]