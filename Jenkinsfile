pipeline {
    agent any

    triggers {
        githubPush()
    }
    
    environment {
        NODE_VERSION = '22'
    }

    stages {
        stage('Install Node.js') {
            steps {
                script {
                    echo "Preparation ..."                
                    echo "Downloading Node.js & npm ..."
                    sh "curl -fsSL https://deb.nodesource.com/setup_${env.NODE_VERSION}.x | sudo -E bash -"
                    echo "Installing Node.js & npm ..."
                    sh "sudo apt-get install -y nodejs"
                }                
            }
        }
        stage('Build') {
            steps {
                echo "Building ..."
                sh "echo 'NPM: $(npm -v)'"
            }
        }
        stage('Test') {
            steps {
                echo "Testing ..."
                echo "Jenkins URL: ${env.JENKINS_URL}"
            }
        }
    }
}