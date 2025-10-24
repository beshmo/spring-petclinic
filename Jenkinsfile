pipeline {

    agent any

    tools {
        maven "MVN";
        jdk "JDK25"
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh './mvnw spring-boot:run'
            }
        }
    }
    
}
