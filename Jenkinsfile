 node {
     stage('Clone repository') {
         echo '> Checking out the Git version '
         checkout scm
     }
     stage('Build') {
          echo '> Building the docker containers ...'
          sh 'docker-compose build'
     }
  
 }
