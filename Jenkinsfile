pipeline {
    agent any
    environment {
        REMOTE_HOST = '65.0.130.110' // Replace with your EC2 instance's IP or hostname
        SSH_KEY = credentials('7155c314-c921-4f68-a3f3-c758dbf91fd9') // Replace with the ID of your SSH private key credential in Jenkins
    }
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    echo "hello-world"
                    // Connect to the remote EC2 instance using SSH
                    sshagent(credentials: [SSH_KEY]) {
                        sh """
                            ssh -o StrictHostKeyChecking=no -i \$SSH_KEY_PATH ec2-user@\$REMOTE_HOST '
                                # Commands you want to execute on the remote instance
                                # For example:
                                echo \"Connected to remote instance.\"
                            '
                        """
                    }
                }
            }
        }
    }
}
