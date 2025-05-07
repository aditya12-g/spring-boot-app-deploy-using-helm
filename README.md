#  Spring Boot App Deployment on AWS EKS using Helm & Jenkins

This project demonstrates how to deploy a Spring Boot application on an AWS EKS cluster using **Helm** for Kubernetes packaging and **Jenkins** for CI/CD automation.

##  Tools & Technologies
- **AWS EKS** – Managed Kubernetes cluster
- **Helm** – Kubernetes package manager
- **Jenkins** – CI/CD pipeline automation
- **Docker** – Containerization of Spring Boot app
- **ECR** – Docker image registry (AWS)
- **Kubernetes** – Container orchestration

##  Project Structure
   spring-boot-app-deploy-using-helm/  
   
   ├── mychart/
   │   ├── Chart.yaml
   │   ├── templates/
   │   └── values.yaml
   ├── src/                      
   ├── Jenkinsfile               
   └── Dockerfile  
   
## For deployment I am using jenkins File 
1 First you have to create the jenkins instance in any cloud platform i am using AWS  
2 Install All the required tools on the jenkins instance  
   EKS Cluster  
   Kubectl  
   eksctl  
   Helm  
   Docker  
   AWS CLI



 
