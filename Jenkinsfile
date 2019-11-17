
pipeline {
    environment {
        //This variable need be tested as string
        doError = '1'
    }
   
    agent any
    
    stages {
        stage('Email Notification') {
            emailext body: '''A new commit has been detected. Proceeding to the pipeline. 
Message generated from the Jenkins pipeline script.''', recipientProviders: [developers()], subject: 'New Commit Found!', to: 'kulsumsiddiqui0016@gmail.com'
        }
        
        stage('Error') {
            when {
                expression { doError == '1' }
            }
            steps {
                echo "Failure"
                error "failure test. It's work"
            }
        }
        
        stage('Success') {
            when {
                expression { doError == '0' }
            }
            steps {
                echo "ok"
            }
        }
    }
    
}





