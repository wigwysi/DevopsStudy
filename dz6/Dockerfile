 FROM ubuntu:20.04
 RUN apt update
 RUN apt install -y default-jdk
 RUN cd /etc/tmp
 RUN mkdir 
 wget  https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.65/bin/apache-tomcat-9.0.65.tar.gz"
 RUN apt install -y maven
 RUN apt install -y git
 RUN cd /etc/
 RUN mkdir projects
 WORKDIR /etc/projects
 RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
 WORKDIR boxfuse-sample-java-war-hello
 RUN mvn package -e
 WORKDIR target
#RUN cp -r hello-1.0 /var/lib/tomcat9/webapps/
 RUN cp hello-1.0.war /var/lib/tomcat9/webapps/
 RUN mkdir /usr/share/tomcat9/conf
 RUN ln -s /etc/tomcat9/server.xml /usr/share/tomcat9/conf/server.xml
 EXPOSE 8080
 CMD ["/usr/share/tomcat9/bin/catalina.sh", "run"]