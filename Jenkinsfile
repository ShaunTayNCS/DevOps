pipeline {
    agent any
 
    tools {
        maven 'Maven 3.6.3' // Adjust the Maven version as needed
    }
 
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/your-repo/your-project.git', branch: 'main'
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
                // Add your deployment steps here
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
