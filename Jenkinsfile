pipeline {
    environment {
        //This variable need be tested as string
        doError = '1'
    }
   
    agent any
    
    stages {
        stage('Email Notification') {
            when {
                expression { doError == '1' }
            }
            steps {
                emailext body: '''A new commit has been detected. Proceeding to the pipeline. 
Message generated from the Jenkins pipeline script.''', recipientProviders: [developers()], subject: 'New Commit Found!', to: 'kulsumsiddiqui0016@gmail.com'
            }
        }
        
        stage('Build') {
            when {
                expression { doError == '1' }
            }
            steps {
                echo "u r in build stage. hi there"
            }
        }
        
        stage('Testing') {
            when {
                expression { doError == '1' }
            }
            steps {
                echo "ur in Testing stage"
            }
        }
        
        stage('Deploy') {
            when {
                expression { doError == '1' }
            }
            steps {
                echo "ur in deployment stage!"
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
            
            emailext body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                recipientProviders: [developers()],
                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",to: 'kulsumsiddiqui0016@gmail.com'
            
        }
    }
}
