# Twitter-Sentiment-Analysis
It refers to a mechanism for transferring data across systems. The data may or may not undergo transformation, and it may be processed in real time (or streaming) as opposed to in batches. Right from harvesting or capturing data using different technologies, storing raw data, cleaning and verifying data, translating data into a queryable format, visualizing KPIs, and orchestrating the aforementioned process is a data pipeline.

# 1. Environment Setup
# 1.1 AWS EC2 instance and security group creation
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

