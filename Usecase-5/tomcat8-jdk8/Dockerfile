FROM ubuntu:16.04
MAINTAINER pictolearn

# Create a directory for JDK installation
RUN mkdir -p /usr/lib/jvm
# Copy the JDK folder from your local machine to the Docker image
COPY java-1.8.0-openjdk-amd64 /usr/lib/jvm/java-1.8.0-openjdk-amd64
# Set the JAVA_HOME environment variable
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk-amd64
# Add JAVA_HOME/bin to the PATH environment variable
ENV PATH $JAVA_HOME/bin:$PATH

RUN apt-get update && apt-get -y upgrade
RUN apt-get -y install software-properties-common
RUN apt-get -y update
RUN apt-get -y install curl vim wget

# Get Tomcat
ENV TOMCAT_VERSION 8.5.0
# Create a directory for Tomcat installation
RUN mkdir -p /opt/tomcat

# Copy the Tomcat folder from your local machine to the Docker image
COPY apache-tomcat-8.5.0 /opt/tomcat