# Use Maven image with Eclipse Temurin JDK 21 as the build stage
FROM maven:3.9.9-eclipse-temurin-21-jammy AS build

# Clone the application source code from GitHub
RUN git clone https://github.com/Rameshmamuduru/My_first_vprofile_project.git

# Switch to the desired branch and build the project, skipping tests
RUN cd My_first_vprofile_project && git checkout containers && mvn clean package -DskipTests


# Use Tomcat 10 with Eclipse Temurin JDK 21 as the runtime image
FROM tomcat:10.1.18-jdk21-temurin-jammy

# Remove default web applications from Tomcat
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy the built WAR file from the build stage to Tomcat's webapps directory as ROOT.war
COPY --from=build /My_first_vprofile_project/target/*.war /usr/local/tomcat/webapps/ROOT.war

# Expose port 8080 for the application
EXPOSE 8080

# Start Tomcat server
CMD ["catalina.sh", "run"]

# Build command: docker build -t myapp:latest -f Docker-files/app/Dockerfile .
