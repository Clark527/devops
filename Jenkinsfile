pipeline {
    agent any
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
                def testImage = docker.build("test-image")
                testImage.push()
            }
                
            }
        }
    }
}
