FROM ubuntu:16.04

LABEL "Maintainer"="Pictolearn"

# Create a directory for JDK installation
RUN mkdir -p /usr/lib/jvm
# Copy the JDK folder from your local machine to the Docker image
COPY jdk1.7.0_80 /usr/lib/jvm/jdk1.7.0_80
# Set the JAVA_HOME environment variable
ENV JAVA_HOME /usr/lib/jvm/jdk1.7.0_80
# Add JAVA_HOME/bin to the PATH environment variable
ENV PATH $JAVA_HOME/bin:$PATH

# Run an update to get all the security patches
RUN apt-get -y update && apt-get -y upgrade && apt-get install -y apt-utils
# Update package lists and install apt-utils
RUN apt-get update && \
    apt-get install -y apt-utils

#Install curl/vim incase you want to debug. VIM - vi editor, curl is a utility which acts as http client which can be run from the unix prompt.
RUN apt-get -y install software-properties-common
#Install CURL and VIM editors
RUN apt-get -y install curl wget vim


ENV TOMCAT_VERSION 7.0.10
# Get Tomcat
# notice that i can add the same RUN command across multiple lines. This is done for Performance optimization
# and does not create too many layers in the image. Use this format if you would like for better maintenance.
# Create a directory for Tomcat installation
RUN mkdir -p /opt/tomcat

# Copy the Tomcat folder from your local machine to the Docker image
COPY apache-tomcat-7.0.10 /opt/tomcat