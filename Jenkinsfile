pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    try {
                        sh 'g++ -o PES1UG22CS523-1 hello.cpp'
                    } catch (Exception e) {
                        error("Build failed: ${e.getMessage()}")
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                sh './PES1UG22CS523-1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
