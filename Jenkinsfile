pipeline {
    agent any
    stages {
        stage('infracost-breakdown') {
            agent {
                docker {
                  image 'infracost/infracost'
                  args '--entrypoint='
                }
            }
            steps {
                sh '/scripts/ci/diff.sh'
            }
        }
    }
}
