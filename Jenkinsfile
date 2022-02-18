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
                    junit 'target/surefire-reports/TEST-*.xml'
                }
            }
        }

      stage('Publish') {
            steps {
                sh './mvnw package'
            }
           post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
      }


    }
}
