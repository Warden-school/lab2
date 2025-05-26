pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-21-alpine'
            args  '-v $WORKSPACE:/workspace --user 0:0'   // keep root, mount code
            /* Make Jenkins start the container *in* /workspace */
            customWorkspace '/workspace'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B clean package'   // no cd needed now
            }
        }
    }
}
