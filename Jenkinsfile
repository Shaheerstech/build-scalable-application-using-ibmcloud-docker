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
                            [5:11 PM, 8/25/2023] Ahsan Khan Boss: mkdir -p ~/.ssh
          echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa
          if [[ $BRANCH_NAME == 'qa.lambdax.ai' ]]; then
            echo "${{ secrets.SSH_KEY_VERTEX }}" > ~/.ssh/id_rsa
          fi
        
          chmod 400 ~/.ssh/id_rsa
          eval "$(ssh-agent -s)"
          ssh-add ~/.ssh/id_rsa
[5:12 PM, 8/25/2023] Ahsan Khan Boss: run: ssh  -o "StrictHostKeyChecking no" -i ~/.ssh/id_rsa ${{ env.EC2_USER }}@${{ env.EC2_HOSTNAME }} 'echo ${{ secrets.DOCKER_PASSWORD }} | sudo docker login --username ${{ secrets.DOCKER_USERNAME }} --password-stdin'
                        """
                    }
                }
            }
        }
    }
}
