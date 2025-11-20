pipeline {
    agent any

    tools {
        maven 'M3'   // nombre EXACTO que pusiste en Maven installations
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/alejandroyahirrosales-sys/Demo-Serenity-Cucumber.git'
            }
        }

        stage('Build & Test') {
            steps {
                bat 'mvn clean verify'
            }
        }

        stage('Report') {
            steps {
                publishHTML([
                    reportDir: 'target/site/serenity',
                    reportFiles: 'index.html',
                    reportName: 'Serenity Report'
                ])
            }
        }
    }
}
