# Use a base image with JDK
FROM openjdk:11-jdk-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the Maven project descriptor files
COPY pom.xml .

# Copy the entire project directory into the container
COPY src ./src

# Build the application with Maven
RUN apt-get update && \
    apt-get install -y maven && \
    mvn clean package

# Expose the port the app runs on
EXPOSE 8080

# Command to run the application
CMD ["java", "-jar", "target/java-keycloak-integration-1.0.0.jar"]
