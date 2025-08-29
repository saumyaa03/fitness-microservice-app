# Use lightweight JDK image
FROM openjdk:21-jdk-slim

# Set working directory
WORKDIR /app

# Copy the JAR built by Maven into the container
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} app.jar

# Expose Eureka port
EXPOSE 8761

# Run the JAR
ENTRYPOINT ["java","-jar","/app.jar"]
