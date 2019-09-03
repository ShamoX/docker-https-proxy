# docker-proxy

this is an easy HTTP proxy docker container that you can use to have multiple docker containers running on a single machine and to proxy requests among the containers.

## how to use

see the following example `docker-compose.yml` file.

```yml
version: '3.3'
services:
  proxy:
    container_name: proxy
    image: shroomlife/docker-proxy:latest
    ports:
      - "80:80"
      - "443:443"
  example.com:
    container_name: example.com.proxy
    image: httpd:latest
```

when your server is reached now at `example.com` all requests will be proxied to your httpd container.
