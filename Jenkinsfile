pipeline {
    agent any

    stages {
        stage('Clone repository'){
          steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/Jatinsharma159/Jenkins.git']]])
          }
        }
    
        stage('Build') {
            steps {
                    build 'PES1UG22CS480 - 1'
                    sh 'g++ -o output hello.cpp'
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploy"
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
