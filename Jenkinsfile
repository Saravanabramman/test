pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the GitHub repository containing your ZIP file
                git branch: 'main', url: 'https://github.com/Saravanabramman/test.git'
            }
        }

        stage('Run Test File') {
            steps {
                // Run the test file
                sh 'python /test.py'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
