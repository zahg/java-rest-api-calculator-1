pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/zahg/java-rest-api-calculator-1.git'
                sh './mvnw clean compile'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }

            post {
                always {
                    junit '/Users/parmjit/Documents/QA-Tests-July2021/BE-test/jenkinsTutorial/java-rest-api-calculator-1/target/surefire-reports/Test-*.xml'
                }
            }
        }
    }
}
