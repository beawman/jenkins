## Jenkins Configuration as Code installation
reference: https://github.com/jenkinsci/configuration-as-code-plugin

```
# local machine
cd jenkins_home
# get file
curl https://github.com/beawman/jenkins/blob/main/002.Configuration-as-Code/plugins.txt -o plugins.txt
# go inside docker
docker exec -it jenkins /bin/bash
# run update command
jenkins-plugin-cli -f /var/jenkins_home/plugins.txt
```
