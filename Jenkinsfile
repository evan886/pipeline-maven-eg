pipeline {
    agent any 

    stages {
       stage('pull code') {
          steps {
             checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '55c4819e-ac29-47c8-97d0-528252de42ef', url: 'http://mygitlab.com/root/pipeline-maven-eg']]])
           }
        
        }
        
        stage('Build') {
            steps {
                sh " /usr/local/maven3/bin/mvn clean  package spring-boot:repackage"
                sh "printenv"
            }

        }
    }
}
