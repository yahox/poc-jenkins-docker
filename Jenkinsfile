pipeline {
    agent {
        // Define the label of the remote JNLP slave
        label 'java-docker-slave'
    }
    stages {
        stage('Test') {
            steps {
                sh 'echo "Running on remote slave" && uname -a'
            }
        }
        stage('Back-end') {
            agent {
                // Define Docker agent for the back-end stage
                docker { 
                    image 'maven:3.8.1-adoptopenjdk-11' 
                }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                // Define Docker agent for the front-end stage
                docker { 
                    image 'node:16-alpine' 
                }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}

