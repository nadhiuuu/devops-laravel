pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('composer:2').inside {
                        sh 'composer install'
                    }
                }
            }
        }
    }
}
