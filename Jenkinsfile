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
                echo "Validate the project"
                sh "mvn validate"
            }
        }

        stage('Package') {
            steps {
                echo "Package the Artifact"
                sh "mvn package"
            }
        }
    }
}
