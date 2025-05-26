pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-21-alpine'  // keep the tiny Linux image
            // Map the Windows workspace to /workspace in the container
            args  "-v ${env.WORKSPACE.replace('C:','/c').replace('\\\\','/')}:/workspace"
            containerWorkDir '/workspace'   // set pwd inside the container
            reuseNode true                  // reuse the same node workspace
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