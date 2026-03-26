FROM jenkins/inbound-agent:latest

USER root

# Install Docker CLI + nginx
RUN apt-get update && \
    apt-get install -y \
        docker.io && \
    apt-get clean

# Allow jenkins user to use docker
#RUN usermod -aG docker jenkins

# Modify existing docker group to match host GID (replace 118 with host GID)
RUN groupmod -g 118 docker \
 && usermod -aG docker jenkins

USER jenkins