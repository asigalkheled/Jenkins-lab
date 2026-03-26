FROM jenkins/inbound-agent:latest

USER root

# Install Docker CLI + nginx
RUN apt-get update && \
    apt-get install -y \
        docker.io && \
    apt-get clean

# Allow jenkins user to use docker
RUN usermod -aG docker jenkins

USER jenkins