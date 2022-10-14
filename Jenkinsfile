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
                DOCKER_PASS = credentials('dockerpass')
            }
            steps {
                sh '''
                    echo "${DOCKER_PASS}"
                '''
            }
        }
    }
}