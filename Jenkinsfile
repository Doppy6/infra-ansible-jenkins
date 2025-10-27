pipeline {
    agent any
    environment {
        ANSIBLE_FORCE_COLOR = 'true'
    }
    stages {
        stage('Checkout Source') {
            steps {
                git branch: 'main', url: 'https://github.com/Doppy6/infra-ansible-jenkins.git'
            }
        }

        stage('Print Working Directory') {
            steps {
                sh 'pwd && ls -lah'
            }
        }
        
        stage('Run Ansible Playbook') {
            steps { 
                    ansiblePlaybook(credentialsId: 'ansible-ssh-key', inventory: 'host.ini', playbook: 'deploy.yml')
                
            }
        }
    }
}
