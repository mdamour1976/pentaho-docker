FROM		pentaho/java5
MAINTAINER	Michael D'Amour <mdamour@pentaho.com>

ADD biserver-ce-2.0.0.stable.tar.gz /pentaho
RUN echo "" > /pentaho/biserver-ce/promptuser.sh

EXPOSE 8080

CMD export PATH=/pentaho/jdk1.5.0_22/bin:$PATH; \
	export JAVA_HOME=/pentaho/jdk1.5.0_22; \
	cd /pentaho/biserver-ce; \
	./start-pentaho.sh; \
	tail -f /pentaho/biserver-ce/tomcat/logs/catalina.out
