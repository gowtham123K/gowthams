pipeline {
    agent any

    environment {
        PYTHON_ENV = "/usr/bin/python3"  // Update with your Python path
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository from GitHub
                git url: 'https://github.com/gowtham123K/gowthams.git', branch: 'main'
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    try {
                        // Run the Python file
                        sh 'python3 hello.py'
                    } catch (Exception e) {
                        error "Python file execution failed: ${e.getMessage()}"
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
