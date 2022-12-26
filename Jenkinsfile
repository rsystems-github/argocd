pipeline {
    agent any
    tools{
        maven 'maven_3_8_6'
    } 
    stages {
        stage('Checkout') { 
            steps {
		checkout([$class: 'GitSCM', branches: [[name: '*/argocd']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rsystems-github/argocd.git']]])
            }
        }
        stage('Update Replicas') { 
            steps {
		sh 'sed -i "s/image: nginx:${OLD_TAG}/image: nginx:${NEW_TAG}/g"  nginx/nginx-deploy.yaml'
		sh 'sed -i "s/replicas: ${OLD_REPLICAS}/replicas: ${NEW_REPLICAS}/g"  nginx/nginx-deploy.yaml'
		sh 'cat nginx/nginx-deploy.yaml'
            }
        }
    }
}
