pipeline {
    agent any
    environment {
        REMOTE_HOST = 'your-ec2-instance-ip'
        SSH_KEY = credentials('your-ssh-credentials-id')
        SSH_USERNAME = 'ec2-user' // Replace with your SSH username
    }
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    echo "hello-world"
                    // Connect to the remote EC2 instance using SSH
                    sshagent(credentials: [SSH_KEY]) {
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
