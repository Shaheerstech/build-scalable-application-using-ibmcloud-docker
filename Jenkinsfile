pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the specified branch
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Replace this with your actual build steps
                sh 'echo "Building the code"'
            }
        }
        
        stage('Notify') {
            when {
                // Only trigger when there's a new commit on any branch
                expression { currentBuild.changeSets.any { it.branch != 'origin/master' } }
            }
            steps {
                script {
                    // Get the branch name of the triggering commit
                    def branchName = currentBuild.changeSets.collect { it.branch }[0]
                    echo "New commit detected in branch: ${branchName}"
                }
            }
        }
    }
}
