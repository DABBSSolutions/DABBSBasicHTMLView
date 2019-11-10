#!/usr/bin/env groovy


node('master'){
    try{
        stage('build'){
            echo "ur in build stage"
        }
        stage('testing'){
            echo "ur in Testing stage"
        }
        stage('deploy'){
            echo "ur in deploy stage"
        }
    }catch{
        echo "an exception was caught!"
    }
}
