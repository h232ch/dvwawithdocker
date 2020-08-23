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
            
            stage('Vulnerability Testing') {
                steps {
                    echo '> Running the application vulnerability tests ...'
                    
                    echo '> 1. Authentification Set ..'
                    bat 'python C:/Users/dnwn7/Desktop/zap/zappython/testpy/zapPython/Auth.py'
                    
                    echo '> 2. Spider ..'
                    bat 'python C:/Users/dnwn7/Desktop/zap/zappython/testpy/zapPython/Spider.py'
                    
                    echo '> 3. Active Scan ..'
                    bat 'python C:/Users/dnwn7/Desktop/zap/zappython/testpy/zapPython/ActiveAttack.py'
                    
                    echo '> 4. Result ..'
                    bat 'python C:/Users/dnwn7/Desktop/zap/zappython/testpy/zapPython/Result.py'
                    bat 'python C:/Users/dnwn7/Desktop/zap/zappython/testpy/zapPython/ResultVuln.py'
                    
                    echo '> Completed!!'
                    
                }
            }
            
        }
    }
