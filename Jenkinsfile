pipeline {
    agent any

    tools {
        jdk 'jdk'           // Must match the name configured in Jenkins
        maven 'Maven-3.9.10'    // Must match the name configured in Jenkins
    }

    
    stages {
        

        stage('Build with Maven') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
