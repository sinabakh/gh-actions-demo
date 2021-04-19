pipeline {
    agent any
    stages {
        stage('infracost-breakdown') {
            agent {
                docker {
                  image 'infracost/infracost'
                  args '--user=root --entrypoint='
                }
            }
            environment {
              INFRACOST_API_KEY = credentials('jenkins-infracost-api-key')
              PATH = 'terraform'
            }

            steps {
                sh '/scripts/ci/diff.sh'
            }
        }
    }
}
