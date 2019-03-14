# Patroni training 2019 edition

Patroni is a template for PostgreSQL HA.
It lives at https://github.com/zalando/patroni.

This repository contains Patroni training materials.

## Prerequisites
  install docker, docker-compose

## (Optional) Build the docker image
  * `git clone https://github.com/zalando/patroni`
  * `cd patroni`
  * `docker build -t patronitraining/patroni .`  

Note that this step is not required, as docker-compose will automatically
fetch the image from the docker-hub. The image there is compressed to save
bandwidth. You can achieve the same with your own image by passing
`--build-arg COMPRESS=1` together with your docker build command, although it
will slightly reduce the image startup time.

## Starting Patroni and etcd with docker-compose
  * `curl -sO https://raw.githubusercontent.com/patroni-training/2019/master/docker-compose.yml (or download it using your preferred tool)`
  * `docker-compose up -d`

## Going further
  * `docker ps` to view the list of running containers.
  * `docker logs -f [container_name]` to view logs from the chosen container.
  * `docker exec -ti [container_name] bash` to exec into the chosen container.

Further details on how the output of those commands should look like are
provided at  [patroni dockerfile README](https://github.com/zalando/patroni/blob/master/docker/README.md#three-node-patroni-cluster-with-three-node-etcd-cluster-and-one-haproxy-container-using-docker-compose).
