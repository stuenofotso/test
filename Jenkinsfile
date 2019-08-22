pipeline {
    agent { docker { image 'maven:3.3.3' }}
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'printenv'
                sh 'mvn compile'
            }
        }
    }
    post {
        always {
            echo 'Ended with status'
        }
        success {
            echo 'success'
        }
        failure {
            echo 'failure'
        }
        unstable {
            echo 'unstable'
        }
        changed {
            echo 'warning: state changed'
        }
    }
}
