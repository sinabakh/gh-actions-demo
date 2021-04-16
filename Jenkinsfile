pipeline {
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
