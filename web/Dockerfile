From ubuntu:latest
ENV dir /opt/tomcat/
WORKDIR $dir
RUN mkdir static
RUN apt-get update
RUN apt-get install zip -y && apt-get install unzip -y 
ADD static.zip /opt/tomcat/static/static.zip
RUN unzip /opt/tomcat/static/static.zip -d /opt/tomcat/static/ && apt-get install openjdk-8-jdk -y && apt-get install curl -y && groupadd tomcat && useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat && cd /tmp && curl -O http://mirrors.estointernet.in/apache/tomcat/tomcat-8/v8.5.35/bin/apache-tomcat-8.5.35.tar.gz && chmod 755 /tmp/apache-tomcat-8.5.35.tar.gz && tar xzvf /tmp/apache-tomcat-8.5.35.tar.gz -C /opt/tomcat --strip-components=1 && cd /opt/tomcat && chgrp -R tomcat /opt/tomcat && chmod -R 755 conf && chmod 755 conf && chown -R tomcat webapps/ work/ temp/ logs/ 
ADD companyNews.war webapps/
COPY server.xml /opt/tomcat/conf/server.xml
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk-amd64/jre
EXPOSE 8082
CMD ["/opt/tomcat/bin/catalina.sh", "run"]
