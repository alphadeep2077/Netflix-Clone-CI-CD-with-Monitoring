# Netflix-Clone-CI-CD-with-Monitoring
We will be deploying a Netflix clone. We will be using Jenkins as a CICD tool and deploying our application on a Docker container and Kubernetes Cluster and we will monitor the Jenkins and Kubernetes metrics using Grafana, Prometheus


![Netflix clone](https://github.com/user-attachments/assets/823c18da-1f59-4abc-9f34-b320b66d2fdb)

#Project Steps :-

#Step 1: Launch an Ubuntu(22.04) T2 Large Instance 


- Launch an Ubuntu(22.04) T2 Large Instance
- Launch an AWS T2 Large Instance. Use the image as Ubuntu. You can create a new key pair or use an existing one. Enable HTTP and HTTPS settings in the Security Group and open all ports (not best case to open all ports but just for learning purposes it's okay).

![image](https://github.com/user-attachments/assets/b8419aac-343c-4b0f-b39e-bc3295463521)

#Step 2 : Install Jenkins, Docker. Create a Sonarqube Container using Docker

- Install Jenkins, Docker and Trivy
- 2A — To Install Jenkins
- Connect to your console, and enter these commands to Install Jenkins

