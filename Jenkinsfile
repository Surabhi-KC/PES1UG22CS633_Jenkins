pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    sh 'git clone https://github.com/Surabhi-KC/PES1UG22CS633_Jenkins.git'
                    dir('YOUR_REPO') {
                        sh 'git checkout main'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                    build 'PES1UG22CS633-1'
                    sh 'exit 1' 
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
