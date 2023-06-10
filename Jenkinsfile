pipeline {
    agent { 
        node {
            label 'docker-agent-new'
            }
      } 
    sleep 3
    environment{
        dockerImage = ' '
        registry = 'jwalant21/new_app'
    }
    
    triggers {
        sleep 3
        pollSCM '* * * * *'
    }
    stages {
        stage('Initialization') {
            steps {
                sleep 3
                echo "hey there from github.."
                sh ''' 
                python3 helloW.py
                '''    
                  }
            }
        stage('Docker Image building'){
            steps{
            echo "building img from dockerfile.."
            sleep 3
            script {
                testImage = docker.build 'target_repo'
                
            }
                
            }
        }
    }
}
