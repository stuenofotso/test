pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn compile'
                mail bcc: '', body: '''Hi,

                Build for project test ended successfully

                Regards''', cc: '', from: '', replyTo: '', subject: '[From jenkins] Build ended', to: 'stuenofotso@gmail.com'
            }
        }
    }
}
