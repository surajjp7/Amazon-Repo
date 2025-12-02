pipeline {
    agent any
    stages {
        
        stage('Clean') {
            steps {
                echo "Cleaning the directory"
                sh "mvn clean"
            }
        }
        
        stage('Compile') {
            steps {
                echo "Compile"
                sh "mvn compile"
            }
        }
        
        stage('Validate') {
            steps {
                echo "Validating the project"
                sh "mvn validate"
            }
        }

        stage('Package') {
            steps {
                echo "Packaging the Artifact"
                sh "mvn package"
            }
        }
    }
    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
