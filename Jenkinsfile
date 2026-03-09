pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                script {
                    docker.image('agung3wi/alpine-rsync:1.1').inside {
                        sshagent(['ssh-pwd']) {
                            sh '''
                            mkdir -p /tmp/.ssh
                            ssh-keyscan -H dev.kelasdevops.xyz >> /tmp/.ssh/known_hosts
                            ssh-keyscan -H prod.kelasdevops.xyz >> /tmp/.ssh/known_hosts
                            '''
                        }
                    }
                }
            }
        }
    }
}