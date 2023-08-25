pipeline {
    agent any
    environment {
        REMOTE_HOST = '65.0.130.110'
        SSH_KEY = credentials('local-cloud-server')
        SSH_USERNAME = 'ec2-user' // Replace with your SSH username
    }
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    echo "hello-world"
                    // Connect to the remote EC2 instance using SSH
                    sshagent(credentials: [AAAAB3NzaC1yc2EAAAADAQABAAABAQCnO41vBzOML8YIlo/4WlkehP8NWwE476VsqMr0WbQp855Wikpq4ZJ/5CUESlIdYVmzNh7ImjiTZpwCd2c5F2FWuDyacM8pB79934hzi2d8WYtFqB7o4+GRjFwohOx0g3lguDe1EoxtTWEItOYxqQk4wF3YG3znVKfD9bYVHcDz1zIOKfwSMrFNYffbufSq5KQdjjprJ/noUAvWmH7hzt0nM/2ZY0rVxv927Hu/RnzPldnO1ofRmRKUBe3SpAa+NDkLgIABzlqrXE1o8Sm52gEHDwibKcdI5FOyEchaUAvMrAUVe0Cah7+kEzsU4iKHTY9cba6/+o99DTne5iqnSYUV open]) {
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
