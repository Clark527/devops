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
            sh '''
            docker build -t my_new_image .
            '''
            }
        
        }
    }
}
