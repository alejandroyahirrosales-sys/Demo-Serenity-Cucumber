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
        bat 'mvn clean verify'
      }
    }
    stage('Report') {
            steps {
                publishHTML(
                    target: [
                        reportDir: 'target/site/serenity',
                        reportFiles: 'index.html',
                        reportName: 'Serenity Report',
                        keepAll: true,                // guarda todos los reportes
                        alwaysLinkToLastBuild: true,  // enlace al último build
                        allowMissing: true            // no rompe si falta el html
                    ]
                )
            }
    }
  }
}
