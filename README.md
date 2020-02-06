# Fluentd
Fluentd docker image with elasticsearch plugin


## Build
`docker build -t fluentd-elasticsearch .`



## Run
`docker run --rm -p 24224:24224 -v fluent.conf:/fluentd/etc/ fluentd-elasticsearch`


## Configuration Files
* Mount fluentd configuration files at /fluentd/etc/ on container


## docker-compose
```
docker-compose up
```