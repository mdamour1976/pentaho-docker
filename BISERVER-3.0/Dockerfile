FROM		pentaho/java5
MAINTAINER 	Michael D'Amour <mdamour@pentaho.com>

ADD biserver-ce-3.0.0-STABLE.tar.gz /pentaho

RUN echo "" > /pentaho/biserver-ce/promptuser.sh

EXPOSE 8080 8099

CMD export PATH=/pentaho/jdk1.5.0_22/bin:$PATH; \
	export JAVA_HOME=/pentaho/jdk1.5.0_22; \
	cd /pentaho/biserver-ce; \
	./start-pentaho.sh; \
	cd /pentaho/administration-console; \
	./start.sh &> pac.log & \
	tail -f /pentaho/biserver-ce/tomcat/logs/catalina.out
