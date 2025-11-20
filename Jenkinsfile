pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/alejandroyahirrosales-sys/Demo-Serenity-Cucumber.git'
            }
        }

        stage('Build & Test') {
            steps {
                bat 'mvn clean verify -Dwebdriver.driver=chrome -Dserenity.headless.mode=true'
            }
        }
    }

    post {
        always {
            publishHTML([
                reportDir: 'target/site/serenity',
                reportFiles: 'index.html',
                reportName: 'Serenity Report',
                keepAll: true,
                alwaysLinkToLastBuild: true,
                allowMissing: true
            ])
        }
    }
}
