#!/usr/bin/env groovy


node('master'){
    try{
        stage('build'){
            echo "u r in build stage."
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
