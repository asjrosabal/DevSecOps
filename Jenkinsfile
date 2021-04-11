pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'NPM Install..'
                sh '''npm install'''
            }
        }

        stage('CodeAnalysis') {
            steps {
                echo 'SonarQube..'
                sh '''
                ./gradlew sonarqube \
                    -Dsonar.projectKey=Jhipterst-test \
                    -Dsonar.host.url=http://localhost:9000 \
                    -Dsonar.login=2a67300911126142d8bfb08549635b08136ffb25
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}