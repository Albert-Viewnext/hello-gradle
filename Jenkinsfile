pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Compilando..'
                sh '''docker-compose build
                docker image tag hello-gradle:latest hello-gradle:main-1.0.${BUILD_NUMBER}-${GIT_COMMIT}
                docker-compose up -d'''
                echo 'Compilado.'
            }
        }
        stage('Test') {
            steps {
                echo 'Probando..'
                echo 'Probado..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Desplegando....'
                sh 'docker-compose up '
                echo 'Desplegado....'
            }
        }
    }
}
