# Use the official Maven image as the base image
FROM maven:3.8.1-openjdk-11 AS build

# Set the working directory
WORKDIR /app

# Copy the project files and download dependencies
COPY pom.xml .
COPY src src/

# Build the project
RUN mvn clean install -DskipTests

# Use the official OpenJDK image as the base image for the final image
FROM openjdk:11-jre-slim

# Set the working directory
WORKDIR /app

# Copy the JAR file from the build image to the final image
COPY --from=build /app/target/spring-boot-server.jar app.jar

# Expose port 8080
EXPOSE 8080

# Command to run the Spring Boot application
CMD ["java", "-jar", "app.jar"]
