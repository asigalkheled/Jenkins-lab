# Create new inbound agent image with python inside
        docker build -t my-python-agent .
# Run  Jenkins Controller

    docker run -d \
     --name inbound-agent-slave \
     -p 5000:5000 \
     -e JENKINS_URL=http://172.17.0.2:8080 \
     -e JENKINS_SECRET=7aba4345add8338b5f63755670efe2f26338d9693d9b0e6b2f1ad228402524e6  \
     -e JENKINS_AGENT_NAME=jenkins-inbound-agent \
     -v jenkins_slave_data:/home/jenkins \
     my-python-agent

# Run Jenkins Job 
http://localhost:8090/job/inbound-agent-python-test/

# Test: open: http://localhost:5000
