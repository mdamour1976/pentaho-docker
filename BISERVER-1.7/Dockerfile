FROM		pentaho/java5
MAINTAINER	Michael D'Amour <mdamour@pentaho.com>

ADD pentaho_demo_hsqldb-1.7.0.GA.tar.gz /pentaho
RUN echo "" > /pentaho/pentaho-demo/promptuser.sh
RUN sed --in-place=.bak 's/sh run.sh/sh run.sh -b 0.0.0.0/' /pentaho/pentaho-demo/start-pentaho.sh

EXPOSE 8080

CMD export JAVA_HOME=/pentaho/jdk1.5.0_22; \
	export PATH=/pentaho/jdk1.5.0_22/bin:$PATH; \
	cd /pentaho/pentaho-demo; \
	./start-pentaho.sh
