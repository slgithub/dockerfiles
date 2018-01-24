#
# OpenJDK Java 8 JRE Dockerfile
#

# Pull base image.
FROM websphere-liberty

COPY server.xml /opt/ibm/wlp/usr/servers/defaultServer/

# Install Java.
RUN apt-get update && apt-get install -y python-software-properties software-properties-common && apt-get install -y openjdk-8-jdk

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
ENV JRE_HOME $JAVA_HOME/jre

ENV PATH=$PATH:$JAVA_HOME/bin
ENV PATH=$PATH:$JRE_HOME/bin


# Define default command.
CMD ["bash"]
CMD ["/usr/bin/java","-version"]
CMD ["export PATH=${PATH /':/opt/ibm/java/jre/bin'/}"]
CMD ["rm -rf opt/ibm/java"]
CMD ["echo \"JAVA_HOME=$(which java)\" | sudo tee -a /etc/environment"]
CMD ["source","/etc/environment"]
CMD ["echo ","$JAVA_HOME"]
CMD ["/opt/ibm/docker/docker-server","run","defaultServer"]
#COPY target/spring-boot-deploy-websphere-liberty-0.0.1.war /opt/ibm/wlp/usr/servers/defaultServer/dropins/

#RUN installUtility install --acceptLicense defaultServer