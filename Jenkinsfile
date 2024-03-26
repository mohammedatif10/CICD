pipeline {
    agent any
    environment {
        JAVA_HOME = "${tool 'jdk11'}"
    }
    tools {
        jdk 'jdk11' // The name of the JDK as configured in Jenkins Global Tool Configuration
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B package --file pom.xml'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
