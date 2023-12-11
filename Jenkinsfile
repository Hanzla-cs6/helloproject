pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Hanzla-cs6/helloproject.git', branch: 'master'
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
                            configName: 'HanzlaSSH',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: '/myapp/')],
                            
                        )
                    ]
                )
            }
        }
    }
}
