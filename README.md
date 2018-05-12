# generate your own Dockerfile without X-Pack (500mo)
https://github.com/elastic/elasticsearch-docker/tree/5.6

`conda create -n elastic python=3.5`

`make dockerfile`


# Docker elastic alpine image (125mo)
https://github.com/blacktop/docker-elasticsearch-alpine

`sudo sysctl -w vm.max_map_count=262144`


# Docker compose: elastic-alpine:5.6 with nginx reverse proxy
https://github.com/robbert229/docker-elk-nginx

https://www.elastic.co/blog/playing-http-tricks-nginx

## Basic authentication, generate your `passwords` file
`sudo apt-get install apache2-utils`

`sudo htpasswd -c passwords <user1>`

`sudo htpasswd passwords <user2>`


