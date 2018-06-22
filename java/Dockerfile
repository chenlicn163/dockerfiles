FROM hub.c.163.com/public/centos:6.7-tools
RUN mkdir -p /var/java 
WORKDIR /var/java
RUN wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie"  http://download.oracle.com/otn-pub/java/jdk/10.0.1+10/fb4372174a714e6b8c52526dc134031e/jdk-10.0.1_linux-x64_bin.tar.gz
RUN wget http://ftp.riken.jp/net/apache/tomcat/tomcat-8/v8.0.52/bin/apache-tomcat-8.0.52.tar.gz
RUN tar -zxvf  jdk-10.0.1_linux-x64_bin.tar.gz
RUN tar -zxvf  apache-tomcat-8.0.52.tar.gz
ENV JAVA_HOME /var/java/jdk-10.0.1
ENV CLASSPATH .:$JAVA_HOME/lib:$JRE_HOME/lib  
ENV PATH $PATH:$JAVA_HOME/bin  
EXPOSE 8080
COPY ./init.sh      /var
ENTRYPOINT ["/bin/bash", "/var/init.sh"]