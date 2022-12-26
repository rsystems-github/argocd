pipeline {
    agent any
    tools{
        maven 'maven_3_8_6'
    }
    stages{
        stage('Checkout'){
            steps{
		checkout([$class: 'GitSCM', branches: [[name: '*/argocd']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rsystems-github/argocd.git']]])
                ///sh 'mvn clean install'
                sh 'pwd'
                sh 'ls'
                sh 'ls nginx'
            }
        }
        ///stage('Build Docker Image'){
            ///steps{
                ///script{
                    ///sh 'docker build -t docker9447/helloworld:v1 . '
		    ///sh 'pwd'
		    ///sh 'ls'
                    ///sh 'ls /home/jenkins/agent/workspace/devops-cicd/webapp/target/webapp.war'
                    ///sh 'docker build -t docker9447/helloworld:v1 . '
                ///}
            ///}
        ///}
        ///stage('Push Docker Image to HUB'){
           /// steps{
              ///  script{
                 ///  withCredentials([string(credentialsId: 'docker_hub_pass', variable: 'docker_hub_pass')]) {
                   ///sh 'docker login -u docker9447 -p ${docker_hub_pass}'
                   ///sh 'docker push docker9447/devops-cicd:v1'
                   ///}
                   ///sh 'docker push docker9447/devops-cicd:v1'
                ///}
            ///}
        ///}
    }
    
}
