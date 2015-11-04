# pentaho-docker
Dockerfile repository for Pentaho images

To build these images you will need to obtain the archive distributions from sourceforge.net.

For example:
```
cd BISERVER-6.0
wget http://iweb.dl.sourceforge.net/project/pentaho/Business%20Intelligence%20Server/6.0/biserver-ce-6.0.0.0-353.zip
docker build -t pentaho:6.0 .
```

To run that same image:
```
docker run -it -p 8080:8080 pentaho:6.0
```

The images have also been pushed to Docker Hub:

https://hub.docker.com/r/pentaho/biserver/


These can be run without doing a local build:
```
docker run -it -p 8080:8080 pentaho/biserver:6.0
```
