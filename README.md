# generate your own Dockerfile without X-Pack (>500mo)
https://github.com/elastic/elasticsearch-docker/tree/5.6

`conda create -n elastic python=3.5`

`make dockerfile`


# Docker elastic alpine image (125mo)
https://github.com/blacktop/docker-elasticsearch-alpine


## increase virtual memory areas

### linux
`sudo sysctl -w vm.max_map_count=262144`

### window docker toolbox

https://github.com/boot2docker/boot2docker/issues/1216

```
docker-machine ssh default
sudo sysctl -w vm.max_map_count=262144
exit
```

## pop-up containers

`docker run -d --name elastic -p 9200:9200 -v "${PWD}"/esdata:/usr/share/elasticsearch/data blacktop/elasticsearch:5.6`

`docker run --name kibana --link elastic:elasticsearch -p 5601:5601 -v "${PWD}"/kibana.yml:/usr/share/kibana/config/kibana.yml docker.elastic.co/kibana/kibana:5.6.9 /bin/bash -c '/usr/share/kibana/bin/kibana-plugin remove x-pack;/usr/local/bin/kibana-docker'`


# Docker compose: elastic-alpine:5.6 with nginx reverse proxy
https://github.com/robbert229/docker-elk-nginx

https://www.elastic.co/blog/playing-http-tricks-nginx

## Basic authentication, generate your `passwords` file
`sudo apt-get install apache2-utils`

`sudo htpasswd -c passwords <user1>`

`sudo htpasswd passwords <user2>`


