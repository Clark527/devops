pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "hey there from github.."
                sh ''' 
                python3 helloW.py
                '''
                
            }
        }
    }
}
