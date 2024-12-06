pipeline {
    agent any

    tools {
        // Ensure the correct JDK version is used
        jdk 'JDK-21' // Replace 'JDK-11' with the name configured in Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the branch
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Compile Java files
                sh 'javac HelloWorld.java'
            }
        }

        stage('Run') {
            steps {
                // Execute the Java program
                sh 'java HelloWorld'
            }
        }
    }

    post {
        always {
            // Archive any artifacts or logs (optional)
            archiveArtifacts artifacts: '**/*.class', allowEmptyArchive: true
        }
        success {
            echo 'Build and Run completed successfully!'
        }
        failure {
            echo 'Build or Run failed.'
        }
    }
}
