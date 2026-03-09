pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                docker.image('agung3wi/alpine-rsync:1.1').inside {
                    sshagent(['ssh-pwd']) {
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