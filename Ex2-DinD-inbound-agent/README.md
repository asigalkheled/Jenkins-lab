# Create new inbound agent image with docker cli + nginx 
        docker build -t dind-inbound-agent .
# Run  Jenkins Controller with Docker socket mounted from host
        docker run -d \
        --name DinD-inbound-node \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -e JENKINS_URL=http://<jenkins-host>:8080 \
        -e JENKINS_SECRET=<your-secret> \
        -e JENKINS_AGENT_NAME=DinD-inbound-node \
        dind-inbound-agent:latest