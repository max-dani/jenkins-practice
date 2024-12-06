pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile the Java program
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Run the Java program
                sh 'java HelloWorld'
            }
        }
    }
}
