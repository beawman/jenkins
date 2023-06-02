# Docker Install
Mac OS
```
brew cask install docker
```
# Jenkins Install
reference: https://www.jenkins.io/doc/book/installing/docker/

Mac OS
```
docker run \
  --name jenkins \
  --restart=on-failure \
  --detach \
  --network jenkins \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client \
  --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 \
  --publish 50000:50000 \
  --volume $(pwd)/jenkins_home:/var/jenkins_home \
  --volume $(pwd)/jenkins_home/certs/client:/certs/client:ro \
  jenkins/jenkins:2.387.3
```
## get initial admin password
```
docker exec -it jenkins /bin/bash
cat /var/jenkins_home/secrets/initialAdminPassword
```
goto: http://localhost:8080/
and enter initial admin password
Then install suggest plugin and waiting for plugin installation
When plugin installation finished, setup new admin user. Input this value
```
username: admin
password: 1234
```
