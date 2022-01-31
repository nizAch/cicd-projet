pipeline {
    agent any

    stages {
        stage('Build') {
            tools {
                maven 'M3'
              }
            steps {
                git branch:'develop', url:'https://github.com/nizAch/cicd-projet'

                bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
