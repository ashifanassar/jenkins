pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"                     // Global Variable : All the stages of the pipeline can inherit this
        SSHCRED = credentials('SSHCRED')
    } 
    options { 
        buildDiscarder(logRotator(numToKeepStr: '3')) 
        disableConcurrentBuilds()
    }
    stages {
        stage("First Stage") {
            steps {
                sh "echo Welcome World!"
                sh "echo ${ENV_URL}"
            }
        }
        stage("Second Stage") {
            environment {
                ENV_URL = "stage.google.com"                // Local Variable :Scope of the local variable is confined to this stage only
            } 
            steps {
                sh "echo We will do CICD Tomorrow using Jenkins"
                sh "echo ${ENV_URL}"
                sh "env"
                sh "sleep 60"
            }
        }
        stage("Third Stage") {
            steps {
                echo "We will do CICD Tomorrow using Jenkins"
            }
        }
    }
}
