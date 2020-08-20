 node {
     stage('Clone repository') {
         echo '> Checking out the Git version '
         checkout scm
     }
     stage('Build') {
         echo '> Build Docker'
         bat 'docker ps -a'
     }
 }
