#!/usr/bin/env groovy


node('master'){
    try{
        stage('build'){
            echo "u r in build stage. hi there"
        }
        stage('testing'){
            echo "ur in Testing stage"
        }
        stage('deploy'){
            echo "ur in deployment stage!"
        }
        stage('Email Notification'){
            mail bcc: '', body: 'Hi there ', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'kulsumsiddiqui0016@gmail.com'
        }
    }catch(error){
        throw error
        echo "an exception was caught!"
    }finally{
        echo "ITS DONE! WEBHOOK is working!!!"
    }
}
