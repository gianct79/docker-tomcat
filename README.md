docker-cups
===========

cups 1.7.1 inside debian:sid

## To Build

```bash
docker build -t "docker-tomcat:1.0" .
```

## To Run

```bash
docker run -it --rm -e SERVER_ENV=dev -p 80:8080 docker-tomcat:1.0
```

## To Debug
docker run -it --rm \
  -e JPDA_ADDRESS=8000 \
  -e JPDA_TRANSPORT=dt_socket \
  -p 80:8080 \
  -p 9000:8000 \
  -v tomcat-users.xml:/usr/local/tomcat/conf/tomcat-users.xml \
  docker-tomcat:1.0 \
  /usr/local/tomcat/bin/catalina.sh jpda run
  