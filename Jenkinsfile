pipeline {

    agent any

    tools {
        maven "MVN";
        jdk "JDK25"
    }

    environment {
        JAVA_HOME = "${tool 'JDK25'}";
        PATH = "${tool 'JDK25'}/bin:${tool 'MVN'}/bin:${env.PATH}"
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
