pipeline{
   agent any
   stages{
      stage('login server'){
         steps{
            sshagent(credentials:['login-cloud-server']){
               sh 'ssh  -o StrictHostKeyChecking=no  root@ip-172-31-42-153 uptime "whoami"'
          }
        echo "success lgoin"
         }
       }
   }
}
