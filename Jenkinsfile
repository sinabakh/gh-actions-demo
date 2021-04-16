pipeline {
    agent {
                docker { image 'infracost/infracost' }
            }
    stages {
        stage('infracost-breakdown') {
            agent {
                docker { image 'infracost/infracost' }
            }
            steps {
                sh "breakdown"
            }
        }
    }
}
