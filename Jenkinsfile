pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Building..."'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Testing..."'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying..."'
            }
        }
    }
    post {
        always {
            echo "committed to Branch"
        }
        when {
            anyOf {
                branch 'Branch A'
                branch 'Branch B'
            }
        }
    }
}
