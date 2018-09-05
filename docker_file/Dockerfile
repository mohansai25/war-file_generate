FROM ubuntu:latest
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get -y install openjdk-8-jdk wget
#ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
RUN mkdir /usr/local/tomcat
RUN wget http://mirrors.sonic.net/apache/tomcat/tomcat-9/v9.0.11/bin/apache-tomcat-9.0.11.tar.gz -O /tmp/tomcat.tar.gz
RUN cd /tmp && tar xvfz tomcat.tar.gz
RUN cp -Rv /tmp/apache-tomcat-9.0.11/* /usr/local/tomcat/
EXPOSE 8080
CMD /usr/local/tomcat/bin/catalina.sh run


# Copy configurations (Tomcat users, Manager app)
COPY tomcat-users.xml /usr/local/tomcat/conf/
COPY context.xml /usr/local/tomcat/webapps/manager/META-INF/
COPY Main.jar /usr/local/tomcat/webapps
#ADD /var/lib/jenkins/workspace/pipeline/Main.jar /usr/local/tomcat/webapps/Main.jar
