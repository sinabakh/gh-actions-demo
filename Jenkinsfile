pipeline {
    agent { docker { image 'golang' } }
    stages {
        stage('infracost-breakdown') {
            agent {
                docker { image 'infracost' }
            }
            steps {
                sh 'infracost help'
            }
        }
    }
}
