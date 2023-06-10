pipeline {
    agent any
    
    environment{
        dockerImage = ' '
        registry = 'jwalant21/new_app'
    }
    
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Initialization') {
            steps {
                echo "hey there from github.."
                sh ''' 
                python3 helloW.py
                '''    
                  }
            }
        stage('Docker Image building'){
            steps{
            echo "building img from dockerfile.."
            
            script {
                testImage = docker.build 'target_repo'
                
            }
                
            }
        }
    }
}
