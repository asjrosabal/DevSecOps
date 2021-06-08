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
                 sh './gradlew clean build --debug'
            }
        }
        stage('SCA Scan') {
            steps {
                sh './gradlew dependencyCheckPurge'
                sh './gradlew dependencyCheckAnalyze'
            }
        }
    }
}
