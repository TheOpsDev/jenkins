# Jenkins Deployement
This repo will allow you to deploy a containerized Jenkins controller with the ability to install multiple plugins at start up.

## Docker commands
### Build image locally
```docker
docker build . -t myjenkins:latest
```
### Launch container
```
docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home myjenkins:latest
```