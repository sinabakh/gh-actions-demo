pipeline {
    agent any
    stages {
        stage('infracost-breakdown') {
            agent {
                docker {
                  image 'infracost-local'
                  args '--user=root --entrypoint='
                }
            }
            environment {
              INFRACOST_API_KEY = credentials('jenkins-infracost-api-key')
            }

            steps {
                sh '/scripts/ci/jenkins_diff.sh terraform'
                sh 'cat infracost_diff_output.html'

                publishHTML (target: [
                    	allowMissing: false,
      		    	alwaysLinkToLastBuild: false,
      			keepAll: true,
      			reportDir: './',
      			reportFiles: 'infracost_diff_output.html',
      			reportName: "Infracost Diff Output"
    		])

            }
        }
    }
}
