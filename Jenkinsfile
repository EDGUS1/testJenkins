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
                //bat "mvn deploy"
                bat "mvn clean package"                
            }
        }
    }
    post {
        always {
            junit 'target/surefire-reports/**/*.xml'
        }
        failure {
            echo 'The Pipeline failed :('
        }
    }
}
