pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Matr1XxxX/PES1UG22CS253_Jenkins.git']]])
            } 
        } 

        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS253-1 main/hello.cp
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22CS253-1' 
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
