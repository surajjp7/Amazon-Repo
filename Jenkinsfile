pipeline {
    agent any

    stages {

        stage('Compile') {
            steps {
                echo "Compile code"
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
}
