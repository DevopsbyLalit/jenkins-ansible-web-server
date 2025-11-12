pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning GitHub repository..."
                git branch: 'main', url: 'https://github.com/DevopsbyLalit/webser-using-ansible-jenkins.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                echo "Running Ansible playbook..."
                sh '''
                ansible-playbook -i inventory/hosts.ini playbooks/web-deploy.yml
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Website deployed successfully on both servers!'
        }
        failure {
            echo '❌ Deployment failed. Check Ansible or Jenkins logs.'
        }
    }
}
