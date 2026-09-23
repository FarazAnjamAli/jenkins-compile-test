pipeline {
    agent any

    environment {
        MAVEN_OPTS = '-Xmx384m'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn -B clean compile'
            }
        }
    }

    post {
        success { echo 'Code compiled successfully.' }
        failure { echo 'Compilation FAILED.' }
    }
}
