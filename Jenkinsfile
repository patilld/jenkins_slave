pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeeoSTr:'3', artifactNumToKeepStr:'3'))
    }
    tools {
        maven 'MAVEN'
    }
    stages {
        stage('Code compilation') {
            steps {
                echo 'Starting code compilation...'
                sh 'mvn clean compile'
                echo 'Code compilation completed successfully!...'
            }
        }
        stage('JUnit execution') {
            steps {
                echo 'Starting JUnit test execution...'
                sh 'mvn clean test'
                echo 'JUnit execution completed successfully!...'
            }
        }
        stage('Build package') {
            steps {
                echo 'Creating artifact...'
                sh 'mvn clean package -DskipTests=true'
                echo 'Artifact created successfully!...'
            }
        }
    }
}