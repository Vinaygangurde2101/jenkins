pipeline {
    agent any

    tools {
        maven "MAVEN"
        jdk "JDK17"
    }

    stages {

        stage('Initialize') {
            steps {
                echo "PATH = ${env.PATH}"
                echo "Maven Home = ${tool 'MAVEN'}"
            }
        }

        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }

    }

    post {
        always {
            junit allowEmptyResults: true, testResults: '**/test-reports/*.xml'
        }
    }
    stage('Build') {
    steps {
        bat 'mvn clean package'
    }
}
}
