pipeline {
    agent any
 
    stages {
        stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/mrvincentoti/lavarel_application_using_ansible.git'
             
          }
        }
        stage('Ansible Init') {
            steps {
                script {
                    def tfHome = tool name: 'Ansible'
                    env.PATH = "${tfHome}:${env.PATH}"
                    sh 'ansible --version' 
                }
            }
        }
        stage('Ansible Deploy') {
            environment {
                DOCKER_PASS = credentials('dockerpass')
            }
            steps {
               sh "ansible-playbook main.yml -i inventories/dev/hosts --user ubuntu --key-file ~/.ssh/id_rsa -e 'DB_PASSWORD=${DOCKER_PASS}' -e '@configs/dev.yml'"            
            }
        }
        // stage('Display Test Credentials') {
        //     environment {
        //         DOCKER_PASS = credentials('dockerpass')
        //     }
        //     steps {
        //         sh '''
        //             echo "${DOCKER_PASS}"
        //         '''
        //     }
        // }
    }
}