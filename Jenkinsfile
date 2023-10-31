pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps{
                // Get some code from a GitHub repo
                git branch: 'main', url: 'https://github.com/AlexGravener/lbg-vat-calculator.git'
            }
        }
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'sonarqube'
            }
            steps {
                withSonarQubeEnv('sonar-qube-alex') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}