pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t first-jenkins:${BUILD_NUMBER} .'
            }
        }

        stage('Docker Save') {
            steps {
                sh 'docker save first-jenkins:${BUILD_NUMBER} -o first-jenkins-${BUILD_NUMBER}.tar'
            }
        }
    }
}