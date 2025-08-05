pipeline {
    agent any
    tools { maven 'M3' } // Use your configured Maven name
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/your-org/your-repo.git'
            }
        }
        stage('Build & Test') {
            steps {
                withMaven(maven: 'M3') {
                    sh 'mvn clean verify'
                }
            }
        }
        // stage('Coverage') {
        //     steps {
        //         // This publishes the JaCoCo XML report found in this path!
        //         recordCoverage tools: [jacoco(pattern: '**/target/site/jacoco/jacoco.xml')]
        //     }
        // }
    }
}
