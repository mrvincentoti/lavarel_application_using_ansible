pipeline {
    agent any
 
    stages {
        stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/mrvincentoti/lavarel_application_using_ansible.git'
             
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