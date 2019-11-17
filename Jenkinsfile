#!/usr/bin/env groovy

doError = '1'

node('master'){
    try{
        stage('Email Notification'){
            emailext body: '''A new commit has been detected. Proceeding to the pipeline. 
Message generated from the Jenkins pipeline script.''', recipientProviders: [developers()], subject: 'New Commit Found!', to: 'kulsumsiddiqui0016@gmail.com'
        }
        stage('build'){
            echo "u r in build stage. hi there"
        }
        stage('testing'){
            when {
                expression { doError == '1' }
            }
            steps
            {
                echo "ur in Testing stage"
            } 
        }
        stage('deploy'){
            echo "ur in deployment stage!"
        }
    }catch(error){
        doError = '0'
        throw error
        echo "an exception was caught!"
    }finally {
            echo 'I will always say Hello again!'
            
            emailext body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                recipientProviders: [developers()],
                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",to: 'kulsumsiddiqui0016@gmail.com'            
    }
}
