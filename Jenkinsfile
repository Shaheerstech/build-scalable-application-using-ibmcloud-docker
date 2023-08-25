pipeline {
    agent any
    environment {
        REMOTE_HOST = '65.0.130.110'
        SSH_KEY = credentials('local-cloud-server')
        SSH_USERNAME = 'Instance-1' // Replace with your SSH username
    }
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    echo "hello-world"
                    // Connect to the remote EC2 instance using SSH
                    sshagent(credentials: [65.0.130.110:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.1]) {
                        sh """
                            ssh -o StrictHostKeyChecking=no -i \$SSH_KEY_PATH \$SSH_USERNAME@\$REMOTE_HOST '
                                # Commands you want to execute on the remote instance
                                echo \"Connected to remote instance.\"
                            '
                        """
                    }
                }
            }
        }
    }
}
