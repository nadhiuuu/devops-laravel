pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {
                    docker.image('agung3wi/alpine-rsync:1.1').inside {
                        sshagent(['prod-key']) {
                            sh '''
                            mkdir -p ~/.ssh
                            ssh-keyscan -H dev.kelasdevops.xyz >> ~/.ssh/known_hosts
                            ssh-keyscan -H prod.kelasdevops.xyz >> ~/.ssh/known_hosts
                            '''
                        }
                    }
                }
            }
        }
    }
}