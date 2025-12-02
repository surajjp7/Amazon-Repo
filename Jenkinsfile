pipeline {
    agent any

    environment {
        git_branch = "main"
        git_url = "https://github.com/surajjp7/Amazon-Repo.git"
        git_credentials = "fcf3f959-d766-4cd6-81e2-2aec30e69b1d"
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Checkout GIT"
                git branch: "${git_branch}", credentialsId: "${git_credentials}", url: "${git_url}"
            }
        }
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
