

pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                script {
                    echo "hello-world"
                    // SSH into the remote EC2 instance and execute commands
                    sshScript = '''
                        ssh -i "ssh-keyscan 65.0.130.110 >> ~/.ssh/known_hosts '
                            # Commands to run on the remote instance
                            # For example:
                            echo "Connected to remote instance"
                            # You can add more commands here
                        '
                    '''
                    sh sshScript
                }
            }
        }
    }
}

