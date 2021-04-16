pipeline {
    agent {
                docker { image 'infracost/infracost' }
            }
    stages {
        stage('infracost-breakdown') {
            agent {
                docker {
                  image 'infracost/infracost'
                  args '--entrypoint=/bin/sh'
                }
            }
            steps {
                sh 'infracost'
            }
        }
    }
}
