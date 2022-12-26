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
        stage('Update Replicas'){
            steps{
                script{
                    sh 'sed -i 's/image: nginx:$OLD_TAG/image: nginx:$NEW_TAG/g'  nginx/nginx-deploy.yaml'
		    sh 'sed -i 's/replicas: $OLD_REPLICAS/replicas: $NEW_REPLICAS/g'  nginx/nginx-deploy.yaml'
		    ///sh 'pwd'
                    ///sh 'docker build -t docker9447/helloworld:v1 . '
                }
            }
        }
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
