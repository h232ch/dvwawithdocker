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
            stage('Build') {
                steps {
                    echo '> Building the docker containers ...'
                    bat 'docker-compose build'
                }
            }
            stage('Test') {
                steps {
                    echo '> Running the application tests ...'
                }
            }
            stage('Depploy') {
                steps {
                    echo '> Deploy Docker ...'
                    bat 'docker-compose up -d'
                    
                }
            }
        }
    }
