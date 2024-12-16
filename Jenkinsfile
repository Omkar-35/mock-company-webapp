pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build the project using Gradle's assemble task
                script {
                    sh './gradlew assemble'
                }
            }
        }

        stage('Test') {
            steps {
                // Run the tests using Gradle's test task
                script {
                    sh './gradlew test'
                }
            }
        }
    }

    post {
        always {
            // This section runs after the pipeline, regardless of the result
            echo 'Pipeline complete.'
        }
        success {
            // Notify on success
            echo 'Pipeline executed successfully.'
        }
        failure {
            // Notify on failure
            echo 'Pipeline failed.'
        }
    }
}
