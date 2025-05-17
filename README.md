# Netflix-Clone-CI-CD-with-Monitoring
We will be deploying a Netflix clone. We will be using Jenkins as a CICD tool and deploying our application on a Docker container and Kubernetes Cluster and we will monitor the Jenkins and Kubernetes metrics using Grafana, Prometheus


![Netflix clone](https://github.com/user-attachments/assets/823c18da-1f59-4abc-9f34-b320b66d2fdb)

# Project Steps :-

## Step 1: Launch an Ubuntu(22.04) T2 Large Instance 


- Launch an Ubuntu(22.04) T2 Large Instance
- Launch an AWS T2 Large Instance. Use the image as Ubuntu. You can create a new key pair or use an existing one. Enable HTTP and HTTPS settings in the Security Group and open all ports (not best case to open all ports but just for learning purposes it's okay).

![image](https://github.com/user-attachments/assets/b8419aac-343c-4b0f-b39e-bc3295463521)

## Step 2 : Install Jenkins, Docker. Create a Sonarqube Container using Docker

- Install Jenkins, Docker and Trivy
- 2A — To Install Jenkins
- Connect to your console, and enter these commands to Install Jenkins

```bash
vi jenkins.sh #make sure run in Root (or) add at userdata while ec2 launch
```

```bash
#!/bin/bash
sudo apt update -y
#sudo apt upgrade -y
wget -O - https://packages.adoptium.net/artifactory/api/gpg/key/public | tee /etc/apt/keyrings/adoptium.asc
echo "deb [signed-by=/etc/apt/keyrings/adoptium.asc] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | tee /etc/apt/sources.list.d/adoptium.list
sudo apt update -y
sudo apt install temurin-17-jdk -y
/usr/bin/java --version
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
                  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
                  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
                              /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y
sudo apt-get install jenkins -y
sudo systemctl start jenkins
sudo systemctl status jenkins
```
```bash
sudo chmod 777 jenkins.sh
./jenkins.sh    # this will installl jenkins
```

- Once Jenkins is installed, you will need to go to your AWS EC2 Security Group and open Inbound Port 8080, since Jenkins works on Port 8080.
- Now, grab your Public IP Address



