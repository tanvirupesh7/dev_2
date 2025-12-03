pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME' // make sure MAVEN_HOME is configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: 'https://github.com/tanvirupesh7/dev_2.git'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling the project...'
                sh 'mvn clean compile'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the package...'
                sh 'mvn package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs!'
        }
    }
}
