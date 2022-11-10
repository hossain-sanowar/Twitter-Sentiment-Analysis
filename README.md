# Twitter-Sentiment-Analysis
It refers to a mechanism for transferring data across systems. The data may or may not undergo transformation, and it may be processed in real time (or streaming) as opposed to in batches. Right from harvesting or capturing data using different technologies, storing raw data, cleaning and verifying data, translating data into a queryable format, visualizing KPIs, and orchestrating the aforementioned process is a data pipeline.

## 1. Environment Setup
### 1.1 AWS EC2 instance and security group creation
- t2.xlarge instance
- 32GB of storage recommended
- Allow ports 4000 - 38888
- chmod 400 twitter_nifi.pem
- Connect to ec2 via ssh: ```ssh -i "D:\path\to\private\key.pem" user@Public_DNS```
- Example: ```ssh -i twitter_nifi.pem ec2-user@ec2-3-72-93-1.eu-central-1.compute.amazonaws.com```
- Port forwarding: ```ssh -i "D:\path\to\private\key.pem" user@Public_DNS```
- Example: ```ssh -i twitter_nifi.pem ec2-user@ec2-3-72-93-1.eu-central-1.compute.amazonaws.com -L 2081:localhost:2041 -L 4888:localhost:4888 -L 2080:localhost:2080 -L 8050:localhost:8050 -L 4141:localhost:4141```
- ```cd docker_exp/```
- Copy from local to ec2: ```scp -r -i "D:\Users\pyerravelly\Desktop\twitter_analysis.pem" ```
- Example:```scp -r -i ~/Downloads/twitter_nifi.pem ~/Documents/Project_Pro/twitter_aws/Codes/docker-exp ec2-user@ec2-3-72-93-1.eu-central-1.compute.amazonaws.com:/home/ec2-user/docker_exp```

### 1.2 Docker installation and running: using docker-compose
- Commands to install Docker:
- ``` cd docker-compose```
- ```sudo yum update -y```
- ```sudo yum install docker```
- ```docker-compose up```

- sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose 
- sudo chmod +x /usr/local/bin/docker-compose 
- sudo gpasswd -a $USER docker 
- newgrp docker
- Start Docker: sudo systemctl start docker
- Stop Docker: sudo systemctl stop docker

### 1.2.1 How to access tools in local machine
- List Docker containers running: ```docker ps```
- CLI access in Docker container: ```docker exec -i -t docker_kafka_1 bash```
- NiFi at: http://localhost:2080/nifi/
- Mongo Express at: http://localhost:4141/
- Jupyter Lab at: http://localhost:4888/lab?
