# Use an official OpenJDK runtime as a parent image
FROM openjdk:17-jdk-slim

# Set the working directory in the container
WORKDIR /app.java

# Copy the Gradle wrapper and other necessary files
COPY gradlew gradlew.bat build.gradle settings.gradle /app/
COPY gradle /app/gradle

# Copy the source code
COPY src /app/src

# Copy other resources like Dockerfile, properties, etc.
COPY . .

# Ensure the Gradle wrapper has executable permissions
RUN chmod +x gradlew

# Build the application using Gradle
RUN ./gradlew clean build

# Expose the port the app runs on (assuming it runs on 8080)
EXPOSE 8080

# Define environment variables
ENV JAVA_OPTS=" "

# Run the application
CMD ["java", "-jar", "AssignmentTest/src/main/java", "my.edu.utar.app"]