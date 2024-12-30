FROM ubuntu:20.04

USER root

# Update and install dependencies
RUN apt update -y && apt install default-jdk -y && apt install wget -y

# Set working directory
WORKDIR /opt/tomcat/

# Download Apache Tomcat from official Tomcat website
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.98/bin/apache-tomcat-9.0.98.tar.gz /opt/tomcat/

# Extract the downloaded Tomcat tarball
RUN tar -xvzf apache-tomcat-9.0.98.tar.gz -C /opt/tomcat/

# Add the application WAR file from Azure Blob Storage
ADD https://storagechibalti.blob.core.windows.net/student/student.war?sp=racwdli&st=2024-12-30T11:38:42Z&se=2024-12-30T19:38:42Z&sv=2022-11-02&sr=c&sig=cfY8HFIDBLvG3be9EFPBPth%2FgXfJVMMUHWyGvlUXjUQ%3D /opt/tomcat/apache-tomcat-9.0.98/webapps/

# Add the MySQL connector JAR file from Azure Blob Storage
ADD https://storagechibalti.blob.core.windows.net/student/mysql-connector.jar?sp=racwdli&st=2024-12-30T11:38:42Z&se=2024-12-30T19:38:42Z&sv=2022-11-02&sr=c&sig=cfY8HFIDBLvG3be9EFPBPth%2FgXfJVMMUHWyGvlUXjUQ%3D /opt/tomcat/apache-tomcat-9.0.98/lib/

# Copy the context.xml configuration
COPY ./context.xml /opt/tomcat/apache-tomcat-9.0.98/conf/context.xml

# Run Tomcat server
CMD ["apache-tomcat-9.0.98/bin/catalina.sh", "run"]

