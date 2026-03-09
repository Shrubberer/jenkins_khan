pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Start OpenShift Build') {
            steps {
                sh '''
                    oc whoami
                    oc project demo-ci
                    oc start-build hello-world --from-dir=. --follow --wait
                '''
            }
        }
    }
}
