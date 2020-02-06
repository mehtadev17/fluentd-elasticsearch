# Fluentd
Fluentd docker image with elasticsearch plugin


## Build
`docker build -t fluentd-elasticsearch .`



## Run
`docker run --rm -p 24224:24224 -v fluent.conf:/fluentd/etc/ fluentd-elasticsearch`


## Configuration Files
* Mount fluentd configuration files at /fluentd/etc/ on container


## docker-compose.yml example
```

elasticsearch:
  image: elasticsearch:6.8.6
  expose:
    - 9200
  ports:
    - "9200:9200"

fluentd:
  image: fluentd-elasticsearch:latest
  volumes:
    - ./fluentd:/fluentd/etc # must have directory fluentd and conf file within ie fluentd/fluent.conf
  depends_on:
    - elasticsearch
  ports:
    - "24224:24224"
    - "24224:24224/udp"
```