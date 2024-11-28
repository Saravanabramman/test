pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the GitHub repository containing your ZIP file
                git branch: 'main', url: 'https://github.com/Saravanabramman/test.git'
            }
        }

        stage('Unzip Files') {
            steps {
                script {
                    // Unzip the downloaded ZIP file into the workspace
                    sh 'unzip test.zip -d ./unzipped_folder'
                }
            }
        }


        stage('Run Test File') {
            steps {
                // Run the test file
                sh 'python unzipped_folder/test.py'
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
