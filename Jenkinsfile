pipeline {
    agent {
        docker { image 'dxheroes/dx-scanner:v3.48.8' }
    }
    stages {
        stage('Test') {
            steps {
                checkout scm
                withCredentials([string(credentialsId: 'dxscanner_api_token', variable: 'DXSCANNER_API_TOKEN'), string(credentialsId: 'GitHub_token', variable: 'GH_TOKEN')]) {
                  sh 'dx-scanner run --ci -r -a $GH_TOKEN -t $DXSCANNER_API_TOKEN'
                }
            }
        }
    }
}
