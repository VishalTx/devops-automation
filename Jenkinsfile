pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/VishalTx/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t vishal7500/devops-integration .'
                }
            }
        }
         stage('Publish image to Docker Hub') { 
            steps {
                withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {
                 sh 'docker push vishal7500/devops-integration'
//         stage('Push image to Hub'){
//             steps{
//                 script{
//                    withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhub')]) {
//                        sh 'docker login -u vishal7500 -p ${dockerhub}'
//                        sh 'docker push vishal7500/devops-integration'
                       
                }
            }
        }
        
//         stage('Deploy to k8s'){
//             steps{
//                 sshagent(['k8config']) {
//                     sh "scp -o StrictHostKeyChecking=no deploymentservice.yaml ubuntu@34.227.109.72:/home/ubuntu"
//                     sh "ls "
//                     script{
//                         try{
//                             sh "ssh ubuntu@34.227.109.72 kubectl apply -f ."}
//                         catch(error){
//                             sh "ssh ubuntu@34.227.109.72 kubectl create -f ."
//                         }
//                     }
//                 }
//             }
//         }
                            
//     // some block
        stage('deploy to k8s'){
            steps{
                withKubeConfig(caCertificate: '', clusterName: '', contextName: '', credentialsId: 'K8SL', namespace: '', restrictKubeConfigAccess: false, serverUrl: '') {
    // some block
                    sh "kubectl apply -f deploymentservice.yaml"
}
                
}               
               

            }
        }
        
}
                
 
