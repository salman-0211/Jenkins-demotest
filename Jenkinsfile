pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/salman-0211/Jenkins-demotest.git'
            }
        }
        stage('Build') {
            steps {
                withMaven(maven: 'Maven3') {
                    bat 'mvn clean install'
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven: 'Maven3') {
                    bat 'mvn test'
                }
            }
        }
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
