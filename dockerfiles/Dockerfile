FROM jenkins/jenkins:lts

LABEL maintainer="Chris Herrera <christian@christian.herrera.com>"
LABEL description="Containerized deployment of a Jenkins Master"
LABEL version="0.1.1"
VOLUME [ "/var/jenkins_home" ]

# Groovy script to specify default number of executors
COPY /resources/executors.groovy /usr/share/jenkins/ref/init.groovy.d/executors.groovy

USER jenkins:jenkins

# Install additional requested plugins from yaml file
COPY /resources/install_plugins.yml /tmp/jenkins_resources/
RUN jenkins-plugin-cli --plugin-file /tmp/jenkins_resources/install_plugins.yml

# 8080 for UI, 50000 for worker node connections 
EXPOSE 8080
EXPOSE 50000