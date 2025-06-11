pipeline {
    agent any
 
    tools {
        maven 'Maven 3.9.4' // Adjust the Maven version as needed
    }
 
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ShaunTayNCS/DevOps.git', branch: 'master'
            }
        }
 
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
 
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
 
        stage('Deploy') {
            steps {
                echo 'Deploy stage placeholder'
            }
        }
    }
 
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}
