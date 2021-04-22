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
              infracost_api_key = credentials('jenkins-infracost-api-key')
              iac_path = "terraform"
            }

            steps {
                sh '/scripts/ci/jenkins_diff.sh'

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
