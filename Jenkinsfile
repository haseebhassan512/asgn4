pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'git@github.com:haseebhassan512/asgn4.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'HaseebINC',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: '/haseeb')],
                        )
                    ]
                )
            }
        }
    }
}
