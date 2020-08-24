    pipeline {
        agent any
     
        options {
            skipDefaultCheckout(true)
        }
     
        stages {
            stage('Git') {
                steps {
                    echo '> Checking out the Git version control ...'
                    checkout scm
                }
            }
            
            stage('Docker Build') {
                steps {
                    echo '> Building the docker containers ...'
                    bat 'docker-compose build'
                }
            }
            
            stage('Docker Depploy') {
                steps {
                    echo '> Deploy Docker ...'
                    bat 'docker-compose up -d'
                    
                }
            }
            
            stage('Functional Testing') {
                steps {
                    echo '> Running the application functional tests ...'
                }
            }
            
            
            
        }
    }
