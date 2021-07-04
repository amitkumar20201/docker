FROM index.docker.io/library/alpine:latest
RUN apk add php
RUN apk add tree
RUN apk add curl

git clone https://github.com/academiaonline/simplilearn-phpinfo/tree/2021-07
cd simple
git checkout 2021-07
docker build --file Dockerfile --tag simplilearn-phpinfo:labs src/
docker run --rm simplilearn-phpinfo:labs which curl php tree

docker container run --detach --entrypoint /usr/bin/php --name simplilearn-phpinfo --publish 80:8080 --volume ${PWD}/src:/src --workdir /src simplilearn-phpinfo:labs -f index.php -S 0.0.0.0:8080

**How to Connect to a Remote Docker Daemon**

From <https://dockerlabs.collabnix.com/beginners/components/daemon/access-daemon-externally.html> 


