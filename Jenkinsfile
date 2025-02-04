pipeline {
    agent any  // Use any available agent

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git url: 'https://github.com/akashS-addweb/Akash-.git', branch: 'main'
            }
        }
        
        stage('Run Script') {
            steps {
                // Run the Python script located in the src directory
                sh 'python3 src/main.py'
            }
        }

        stage('Archive Results') {
            steps {
                // Archive the output files (if any)
                archiveArtifacts artifacts: '**/output.txt', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}

