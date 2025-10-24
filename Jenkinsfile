pipeline {

    agent any

    tools {
        maven "MVN";
        jdk "JDK25"
    }

    environment {
        JAVA_HOME = "/var/jenkins_home/tools/hudson.model.JDK/JDK25/jdk-25.0.1";
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
