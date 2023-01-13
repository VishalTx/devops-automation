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
        stage('kuch bhi'){
            steps{
                kubeconfig(caCertificate: 'LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUMvakNDQWVhZ0F3SUJBZ0lCQURBTkJna3Foa2lHOXcwQkFRc0ZBREFWTVJNd0VRWURWUVFERXdwcmRXSmwKY201bGRHVnpNQjRYRFRJek1ERXhNREV4TXpNME1sb1hEVE16TURFd056RXhNek0wTWxvd0ZURVRNQkVHQTFVRQpBeE1LYTNWaVpYSnVaWFJsY3pDQ0FTSXdEUVlKS29aSWh2Y05BUUVCQlFBRGdnRVBBRENDQVFvQ2dnRUJBTmI2CklYT0JpYnpwTnV6eERiMXdJUWdyQnIwRllLUUN6MnVySzdMWGo5OGZEWDNHYVdzYnMwSThqc3c4MTZIRDlWeVIKTmE5eERHalk3VEQ3YXNSeTZUcTdnWnVpZExod1BVb1BlUlM3ZVBybG04VmhLdjF5dHloYi8rSVZhdmh2OW96cAprVVptY3ArRzlVczIvWUM5UUtTL084emkwZWRDSklaTnFCUDE1WGRFZ2Y1OCs1cEVJVkU1SXB2dGVFbUM5WGZnCjhKMFlWanY5bnBDWVYvZjZRb3EvWFFDZERPZUhYS1Y1aWxHYXNRV0FMd2JSVk1FcVZjTzBjZXpuRHdqNE5Lb3AKbFFiZGJjQTR4aVJMNFVoVTJGbkl6TlBMQndwQ2p1RHA0M21TbzJUUzhXNXpvTklXWWhuaXQrYjNCKzFTVU4zQwpuYTRycUs4RmhjY0dIK0ZsdW44Q0F3RUFBYU5aTUZjd0RnWURWUjBQQVFIL0JBUURBZ0trTUE4R0ExVWRFd0VCCi93UUZNQU1CQWY4d0hRWURWUjBPQkJZRUZQbVJsNXNwMHlWMnBJVkdmOXcvUHZzcmZRa0JNQlVHQTFVZEVRUU8KTUF5Q0NtdDFZbVZ5Ym1WMFpYTXdEUVlKS29aSWh2Y05BUUVMQlFBRGdnRUJBTTNHejJYUGxyY0I2Tmp5R05rVwpMOUtEUWEyKytXTUZCeENhdDlFVy9lSmpYaG04alBucHNWdjJqKzN4VjV1ZXZGYnMxV2pvSDN2dmZsKzRBMWtuCnp0Q2RET2Y2UGNUQzVNNW5HNWRtOUVaWTcwNHlzTGt2d0FTcVJCQWo2OTdiSDFwcUpvNkVMOWpVN0t5NGRiamQKbzJFaWM0a25KWWI4aHVtTW8xWWs4cFNuQ0oyNldFelYwSUpyaXVDUTRiejJ6ZWRFbE1nOVZ2cWxiTmZJMk1NOApLZGhIR2ZabTd1dlZMK01iQlJwcWxWZllOQU1HbitPRHpLU1lzRW1UdjljYkZrQVRaN0hGanZISXhHOHorMzlmCm02SndyMkl4enhiWVo0dEZZblZHd1N3MExCeW9zQVhmczdzaE9jRXFYbnozRjhTS3NGM2ZZWUJobWF4WUR5REEKME80PQotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0tCg==', credentialsId: 'K8SL', serverUrl: '') {
    // some block
                sh "pwd"
//                 sh "kubectl apply -f deploymentservice.yaml"
}               
               

            }
        }
        
}
                
 }





