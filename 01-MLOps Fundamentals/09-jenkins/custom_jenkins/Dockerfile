# Ref: https://hackmamba.io/blog/2022/04/running-docker-in-a-jenkins-container/
FROM jenkins/jenkins:lts
USER root
RUN curl https://get.docker.com > docker_install && chmod 777 docker_install && ./docker_install
USER jenkins
