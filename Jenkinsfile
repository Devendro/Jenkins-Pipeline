pipeline {
    agent any
    tools {
        maven "maven_home"
        jdk "Jdk_home"
    }
    stages {
        stage('Stage 1 - INITIALIZATION') {
            steps {
                input('Do you want to proceed?')
                echo 'THIS IS THE DEMO OF MAVEN PIPELINE USING JENKINS'
            }
        }
        stage('Stage 2 - COMPILE CODE') {
            steps {
                bat "mvn compile"
            }
        }
        stage('Stage 3 - UNIT TEST') {
            steps {
                echo "Running Unit Test"
                bat "mvn test"
            }
        }
        stage('Stage 4 - INTEGRATION TEST') {
            steps {
                echo "Running Integration Test"
                bat "mvn verify"
            }
        }
        stage('Stage 5 - CREATE BUILD') {
            steps {
                echo "Creating a build"
                bat "mvn package"
            }
        }
    }
    post {
        failure {
            echo "Email has been sent for Jenkins build failure"
        }
    }
}
