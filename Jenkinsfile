pipeline {
    agent any
    options {
        ansiColor('xterm')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Compilando..'
                sh './gradlew assemble'

                /* sh '''docker-compose build
                docker image tag hello-gradle:latest hello-gradle:main-1.0.${BUILD_NUMBER}-${GIT_COMMIT}
                docker-compose up -d'''
                echo 'Compilado.'
                */
            }
        }

        stage('Archive') {
            archiveArtifacts artifacts: 'build/libs/*.jar'
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
