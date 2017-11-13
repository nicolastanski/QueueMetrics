# Instalação QueueMetrics 17

## Ambiente
Debian 8 Wheezy x86_64  
Queuemetrics 17.06.1  
Tomcat 8.5.23  
Java JDK 8u151  

## Instalação Java JDK 8

\# cd /usr/src  
\# wget http://download.oracle.com/otn-pub/java/jdk/8u151-b12/e758a0de34e24606bca991d704f6dcbf/jdk-8u151-linux-x64.tar.gz  
\# tar -zxvf jdk-8u151-linux-x64.tar.gz  
\# mv jdk1.8.0_151 /usr/lib/jvm/  

\# update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_151/bin/java" 1  
\# update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.8.0_151/bin/javac" 1  
\# update-alternatives --install "/usr/bin/jar" "jar" "/usr/lib/jvm/jdk1.8.0_151/bin/jar" 1  
\# update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/lib/jvm/jdk1.8.0_151/bin/javaws" 1  


## Instalação Tomcat 8

\# cd /usr/src  
\# wget http://mirror.nbtelecom.com.br/apache/tomcat/tomcat-8/v8.5.23/bin/apache-tomcat-8.5.23.zip  
\# unzip apache-tomcat-8.5.23.zip  
\# mv apache-tomcat-8.5.23 tomcat8  
\# mv tomcat8 /var/lib/  
\# ln -s /var/lib/tomcat8/bin/catalina.sh /etc/init.d/tomcat8  


## Instalação MySQL Server

\# apt-get update  
\# apt-get install mysql-server  

Defina uma senha para o usuário root do MySQL.  


## Instalação QueueMetrics

\# cd /usr/src  
\# wget http://downloads.loway.ch/qm/QueueMetrics-17.06.1.tar.gz  
\# tar -zxvf QueueMetrics-17.06.1.tar.gz  
\# mv queuemetrics* queuemetrics  
\# mv queuemetrics /var/lib/tomcat8/webapps/queuemetrics  


## Instalação Mysql Connector

\# cd /usr/src  
\# wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz  
\# tar -zxvf mysql-connector-java-5.1.44.tar.gz  
\# cd mysql-connector-java-5.1.44  
\# cp mysql-connector-java-5.1.44-bin.jar /var/lib/tomcat8/webapps/queuemetrics/WEB-INF/lib/  


## Acesso
http://IP_SERVER:8080/queuemetrics  
Usuário: demoadmin  
Senha: demo  


Fontes: http://www.blogopcaolinux.com.br/2017/06/Como-instalar-o-Oracle-Java-JDK-no-Debian.html
