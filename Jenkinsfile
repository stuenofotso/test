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
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'target/classes/*', fingerprint: true
            //junit 'build/reports/**/*.xml'
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
