pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'
    }

    stages {

        stage('Initialize') {
            steps {
                echo "Initializing the pipeline"
                sh '''
                echo "Java Version:"
                java -version
                echo "Maven Version:"
                mvn -version
                '''
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/username/repository.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

    }
}
