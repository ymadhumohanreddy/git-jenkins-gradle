pipeline {
    agent any

    tools {
        gradle 'Gradle 8.13' // Make sure Jenkins has this tool configured
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ymadhumohanreddy/git-jenkins-gradle.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }
    }

    post {
        success {
            echo 'Build and Test successful!'
        }
        failure {
            echo 'Build or Test failed.'
        }
    }
}
