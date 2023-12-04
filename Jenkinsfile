pipeline {
    agent any
  
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
      
        stage("Build") {
            steps {
                sh 'echo Build......'
            }
        }
      
        stage("Unit Tests") {
            steps {
                sh 'echo Testing......'
            }
        }
      
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarScanner'
                    withSonarQubeEnv('SonarScanner') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
