pipeline {
    agent any

    stages {

        stage('Clean') {
            steps {
                echo "Cleaning the directory on Branch: ${env.BRANCH_NAME}"
                sh "mvn clean"
            }
        }

        stage('Compile') {
            steps {
                echo "Compile the code"
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

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying the artifact only for MAIN branch"
            }
        }
    }
}
