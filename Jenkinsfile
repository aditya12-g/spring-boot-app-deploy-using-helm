pipeline {
    agent any
    
    tools {
        maven 'Maven3'
    }
    
    environment {
        registry = '343218224833.dkr.ecr.ap-south-1.amazonaws.com/my-docker-repo'  # 343218224833 should be replaced by your account ID
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aditya12-g/spring-boot-app-deploy-using-helm.git'
            }
        }

        stage('Build Jar') {
            steps {
                sh 'mvn clean install'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("${registry}:${env.BUILD_NUMBER}")
                }
            }
        }
        
         stage('Pushing Image To ECR') {
            steps {
                script {
                    sh "aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 343218224833.dkr.ecr.ap-south-1.amazonaws.com"
                    sh " docker push 343218224833.dkr.ecr.ap-south-1.amazonaws.com/my-docker-repo:${env.BUILD_NUMBER}"
                }
            }
        }
        
         stage('Helm Deployment') {
            steps {
                script {
                     sh "helm upgrade first --install mychart --namespace helm-deployment --set image.tag=${env.BUILD_NUMBER}"
                }
            }
        }
    } 
}    
