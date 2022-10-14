pipeline {
    agent any
 
    options {
        skipDefaultCheckout(true)
    }
 
    stages {
        stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/devops4solutions/Ansible-Sample-Application-Deployment.git'
             
          }
        }
        stage('Display Test Credentials') {
            environment {
                MYAPP_SSH_PRIVATE_KEY = credentials('dockerpass')
            }
            steps {
                sh 'echo MYAPP_SSH_PRIVATE_KEY'
            }
        }
    }
}