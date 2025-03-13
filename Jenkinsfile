pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    sh 'git clone https://github.com/Surabhi-KC/PES1UG22CS633_Jenkins.git'
                    dir('PES1UG22CS633_Jenkins_1') {  
                        sh 'git checkout main'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS633-1'
                sh 'g++ -o output main.cpp'  
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
                echo 'Deploy'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'  
        }
    }
}
