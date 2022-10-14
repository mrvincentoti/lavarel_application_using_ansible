pipeline {
    agent any
 
    options {
        skipDefaultCheckout(true)
    }
 
    stages {
        stage('checkout') {
           steps {
             
                git 'https://github.com/mrvincentoti/lavarel_application_using_ansible.git'
             
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