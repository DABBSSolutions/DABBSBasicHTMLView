#!/usr/bin/env groovy


node('master'){
    try{
        stage('Email Notification'){
            mail bcc: '', body: 'A new commit has been detected. Proceeding to process the repository through pipeline.', cc: '', from: 'daniyalakbar1217@gmail.com', replyTo: '', subject: 'Jenkins Job', to: 'kulsumsiddiqui0016@gmail.com'
        }
        stage('build'){
            echo "u r in build stage. hi there"
        }
        stage('testing'){
            echo "ur in Testing stage"
        }
        stage('deploy'){
            echo "ur in deployment stage!"
        }
    }catch(error){
        throw error
        echo "an exception was caught!"
    }finally{
        echo "ITS DONE! WEBHOOK is working!!!"
    }
}
