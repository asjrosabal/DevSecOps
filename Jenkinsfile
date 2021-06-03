pipeline {
    agent any
    tools {nodejs "NodeJs"}
    stages {
        stage('Build Front') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build Back') {
            steps {
                sh './gradlew build --scan'
            }
        }
    }
}
