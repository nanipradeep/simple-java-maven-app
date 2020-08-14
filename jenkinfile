pipeline {
    agent any
    stages {
        stage ('master')
        {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true clean install'
            }
            post {
                success{
                    archiveArtifacts artifacts: 'target/**/*.jar', fingerprint: true
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
