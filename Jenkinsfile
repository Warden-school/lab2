pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-21-alpine'
            args "-v ${env.WORKSPACE.replace('C:','/c').replace('\\\\','/')}:/workspace -w /workspace"
            reuseNode true
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn -B clean package'
            }
        }
    }
}
