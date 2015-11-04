FROM		pentaho/java7
MAINTAINER	Michael D'Amour <mdamour@pentaho.com>

# install postgresql
RUN apt-get -y -q install postgresql-9.3 postgresql-client-9.3 postgresql-contrib-9.3

ADD biserver-ce-5.1.0.0-752.tar.gz /pentaho
ADD pg_hba.conf /etc/postgresql/9.3/main/pg_hba.conf

# setup postgres, populate with scripts
RUN echo "listen_addresses='*'" >> /etc/postgresql/9.3/main/postgresql.conf
RUN /etc/init.d/postgresql start; \
	cd /pentaho/biserver-ce/data/postgresql; \
	psql -U postgres -f create_jcr_postgresql.sql; \
	psql -U postgres -f create_quartz_postgresql.sql; \
	psql -U postgres -f create_repository_postgresql.sql; \
	psql -U postgres -f pentaho_mart_postgresql.sql; \
	/etc/init.d/postgresql stop

# force platform to not prompt user at first startup
RUN rm /pentaho/biserver-ce/promptuser.sh

RUN touch /pentaho/biserver-ce/tomcat/logs/catalina.out

EXPOSE 8080

CMD /etc/init.d/postgresql start; \
	cd /pentaho/biserver-ce; \
	./start-pentaho.sh; \
	tail -f /pentaho/biserver-ce/tomcat/logs/catalina.out
