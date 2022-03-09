pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                bat "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
              
                    bat "mvn test"
                
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven:"M3"){
                    bat "mvn deploy"
                }
            }
        }
    }
    post {
        always {
            junit '**/target/*.xml'
        }
        failure {
            echo 'The Pipeline failed :('
        }
    }
}
