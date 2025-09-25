# Install jenkins using docker image : install docker 
<pre>
sudo apt-get update
sudo apt-get install docker.io -y
sudo usermod -aG docker $USER && newgrp docker
</pre>
# Pull docker images 
 docker pull jenkins/jenkins:lts 
# Docker images run : 2 ports 1: jenkins 2: agent
docker run -d -p 8080:8080 -p 5000:5000 --name jenkins -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
# Unlock Jenkins -> /var/jenkins_home/secrets/initialAdminPassword
docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
# Install plugin 
