pipeline {
    agent any
    tools { maven 'M3' } // Use your configured Maven name
    stages {
        stage('Sanity Check') {
            steps {
                echo "I am inside the Jenkinsfile!"
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/vwagh-dev/hello-world.git'
            }
        }
        stage('Build & Test') {
            steps {
                withMaven(maven: 'M3') {
                    sh 'mvn clean verify'
                }
            }
        }
        stage('Coverage') {
            steps {
                // This publishes the JaCoCo XML report found in this path!
                recordCoverage tools: [jacoco(pattern: '**/target/site/jacoco/jacoco.xml')]
            }
        }
    }
}
