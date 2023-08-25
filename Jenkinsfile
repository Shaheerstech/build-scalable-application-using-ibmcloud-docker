pipeline{
   agent any
   stages{
      stage('login server'){
         steps{
            sshagent(credentials:['login-cloud-server']){
               sh 'ssh  -o StrictHostKeyChecking=no  root@135.181.203.3 uptime "whoami"'
          }
        echo "success lgoin"
         }
       }
   }
}
