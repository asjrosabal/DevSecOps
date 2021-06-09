pipeline {
    agent any
    tools {nodejs "NodeJs"}
    stages {
        stage('Build Front') {
            steps {
                sh 'npm install'
            }
        }
        /*stage('Build Back') {
            steps {
                 sh './gradlew clean build --debug'
            }
        }*/
          stage('SAST'){
        sh ''' ./gradlew sonarqube \
          -Dsonar.projectKey=github2 \
          -Dsonar.host.url=http://localhost:9000 \
          -Dsonar.login=1890805ea65026d01d5d91a5bdc52f66c42659bb 
          '''
      }
        stage('SCA Scan') {
            steps {
                sh './gradlew dependencyCheckPurge'
                sh './gradlew dependencyCheckAnalyze'
            }
        }
    }
}
