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
   ```bash
spring-boot-app-deploy-using-helm/
├── mychart/                # Helm chart for the app
│   ├── Chart.yaml          # Chart metadata
│   ├── templates/          # Kubernetes manifests (deployment, service, etc.)
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   └── _helpers.tpl
│   └── values.yaml         # Customizable Helm values
├── src/                    # Spring Boot source code
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/demo/
│   │   │       ├── DemoApplication.java
│   │   │       └── controller/
│   │   │           └── HelloController.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── static/
│   └── test/
│       └── java/
├── Dockerfile              # Dockerfile to build the Spring Boot app image
├── Jenkinsfile             # Jenkins pipeline for CI/CD
├── README.md               # Project documentation
└── pom.xml                 # Maven build file
```

   
## For deployment I am using jenkins File 
1 First you have to create the jenkins instance in any cloud platform i am using AWS  
2 Install All the required tools on the jenkins instance  
   EKS Cluster  
   Kubectl  
   eksctl  
   Helm  
   Docker  
   AWS CLI  
3 I am providing you whole jenkins file in Folder FILENAME Jenkinsfile  
  simpaly you have to copy and paste in pipeline script at jenkins make sure you install all the required plugins in jenkins such as docker,dockerpipeline, maven  
## Now How to rollback to the previous version  
Check Helm release history:  
```bash
helm history first -n helm-deployment
```
Roll back to a previous revision (e.g., revision 1):  
```bash
helm rollback first 1 -n helm-deployment
```
Confirm the rollback:  
```bash
helm list -n helm-deployment
kubectl get pods -n helm-deployment
```
## Adding Scrrenshots of my RESULTS  
First Relese  
![image alt](https://github.com/aditya12-g/spring-boot-app-deploy-using-helm/blob/main/Screenshot%20(62).png?raw=true)  
Second Relese after changing the code  
![image alt](https://github.com/aditya12-g/spring-boot-app-deploy-using-helm/blob/main/Screenshot%20(63).png?raw=true)  
While Rollbacking the previous release  
![image alt]()







 
