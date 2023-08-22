pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                echo 'This is build stage'
            }
        }
        stage('test') {
            steps {
                echo 'Test stage'
            }
        }
        stage('deploy') {
            steps {
                def dockerCMD = "docker run -p 3000:3000 -d  musman6163/my-repo:v2"
                sshagent(['ec2-server-key']) {
                    sh "ssh ec2-user@15.168.13.66 ${dockerCMD}"
               }
            }
        }
    }
}
