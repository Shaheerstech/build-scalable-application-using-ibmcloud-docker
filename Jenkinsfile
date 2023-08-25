pipeline {
   agent any
   stages {
stage('Install dependencies') {
  steps {
    script {
     
     echo "hello-world"
          //stages
            sh '''
            mkdir -p ~/.ssh
          echo "${{ secrets.SSH_KEY }}" > ~/.ssh/id_rsa
          if [[ $BRANCH_NAME == 'qa.lambdax.ai' ]]; then
            echo "${{ secrets.SSH_KEY_VERTEX }}" > ~/.ssh/id_rsa
          fi
        
          chmod 400 ~/.ssh/id_rsa
          eval "$(ssh-agent -s)"
          ssh-add ~/.ssh/id_rsa
          run: ssh  -o "StrictHostKeyChecking no" -i ~/.ssh/id_rsa ${{ env.EC2_USER }}@${{ env.EC2_HOSTNAME }} 'echo ${{ secrets.DOCKER_PASSWORD }} | sudo docker login --username ${{ secrets.DOCKER_USERNAME }} --password-stdin'

             


             
                '''
      
    }
  }
}




      
   }
}
