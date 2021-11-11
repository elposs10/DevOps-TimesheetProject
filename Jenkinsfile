pipeline {
    agent any
    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...';
                git branch: 'oussema',
                url: 'https://github.com/elposs10/DevOps-TimesheetProject.git';
            }
        }
        stage("Test, Build") {
            steps {
                bat "mvn clean install"
            }
        }
        stage("Package") {
            steps {
                bat "mvn package"
            }
        }
    }
    post {
        success {
            emailtext body:'Build Success', subject:'Jenkins', to: 'oussema.mihoubi@esprit.tn'
        }
        failure {
            emailtext body:'Build Failure', subject:'Jenkins', to: 'oussema.mihoubi@esprit.tn'
        }
    }
}