pipeline {
    agent {
        docker { image 'dxheroes/dx-scanner:v3.48.8' }
    }
    stages {
        stage('Test') {
            steps {
                checkout scm
                sh 'dx-scanner run --ci -r --fail=off'
            }
        }
    }
}
