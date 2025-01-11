pipeline {
    agent { label 'jenkins-agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }

    stages {
        stage("cleanup workspace"){
            steps {
            cleanws()
            }
        }
        stage("Checkout from SCM"){
            steps {
            git credentialsId: 'github', url: 'https://github.com/Sangamvirat/django.git'
            }
        }
        stage("Build appliction"){
            steps {
            sh "mvn clen package"
            }
        }
        stage("Test applictaion"){
            steps {
                sh "mvn tesr"
            }
        }
    }
}
