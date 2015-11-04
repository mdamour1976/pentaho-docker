FROM		pentaho/java5
MAINTAINER	Michael D'Amour <mdamour@pentaho.com>

ADD pentaho_demo-1.2.0.534-GA.tar.gz /pentaho

EXPOSE 8080

CMD export JAVA_HOME=/pentaho/jdk1.5.0_22; \
	export PATH=/pentaho/jdk1.5.0_22/bin:$PATH; \
	cd /pentaho/pentaho-demo; \
	./start-pentaho.sh
