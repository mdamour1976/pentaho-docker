FROM		pentaho/java6
MAINTAINER	Michael D'Amour <mdamour@pentaho.com>

ADD biserver-ce-4.5.0-stable.tar.gz /pentaho

RUN echo "" > /pentaho/biserver-ce/promptuser.sh

EXPOSE 8080 8099

CMD export PATH=/pentaho/jdk1.6.0_45/bin:$PATH; \
	export JAVA_HOME=/pentaho/jdk1.6.0_45; \
	cd /pentaho/biserver-ce; \
	./start-pentaho.sh; \
	cd /pentaho/administration-console; \
	./start-pac.sh &> pac.log & \
	tail -f /pentaho/biserver-ce/tomcat/logs/catalina.out
