# ElasticSearch dockerfile

This image contains a default configuration of ElasticSearch based on [jakubzapletal/java:openjdk-7-jre](https://github.com/jakubzapletal/docker-java/tree/openjdk-7-jre)
Comes bundled with [ElasticHQ](https://github.com/royrusso/elasticsearch-HQ)
and [Marvel](https://www.elastic.co/downloads/marvel)

## Using the Docker Hub
 
This image is published under [Jakub Zapletal's repository on the Docker Hub](https://hub.docker.com/u/jakubzapletal/) and all you need as a prerequisite is having Docker installed on your machine.
The container exposes the following ports:

- `9200`: HTTP transport and ElasticHQ (`http://localhost:9200/_plugin/HQ/`)
- `9300`: Native transport protocol

There is the prepared volume `/data` for saving data into a local machine.

To start a container with this image you just need to run the following command:

```bash
docker run -d -p 9200:9200 -p 9300:9300 -v <LOCAL_PATH>:/data --name elasticsearch jakubzapletal/elasticsearch
```

If you already have services running on your host that are using any of these ports, you may wish to map the container
ports to whatever you want by changing left side number in the `-p` parameters. Find more details about mapping ports
in the [Docker documentation](http://docs.docker.com/userguide/dockerlinks/).

## Building the image yourself

The Dockerfile and supporting configuration files are available in the Github repository. This comes specially handy if you want to change any configuration or simply if you want to know how the image was built.
