pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9'
        jdk '17'
    }
    stages {
        stage('Clonar') {
            steps {
                git branch: 'main', url: 'https://github.com/MarceloBravo/saludoapp'
            }
        }
        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            echo "El build fue exitoso"
        }
        failure {
            echo "El build falló"
        }
    }
}
