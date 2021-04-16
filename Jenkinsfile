pipeline {
    gent {
                docker { image 'infracost' }
            }
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
