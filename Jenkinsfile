pipeline {
    agent any

    tools {
        jdk 'jdk'                 // Must match Jenkins Global Tool name
        maven 'Maven-3.9.10'      // Must match Jenkins Global Tool name
    }

    environment {
        GIT_REPO = 'https://github.com/himanshugude/simple-java-project-1.git'
        MAVEN_HOME = tool 'Maven-3.9.10'
        JAVA_HOME = tool 'jdk'
        PATH = "${env.PATH};${MAVEN_HOME}\\bin;${JAVA_HOME}\\bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
