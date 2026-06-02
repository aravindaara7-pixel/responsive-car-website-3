pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/aravindaara7-pixel/responsive-car-website-3.git'
            }
        }

        stage('Verify Files') {
            steps {
                sh '''
                echo "Current Directory:"
                pwd

                echo "Project Files:"
                ls -la
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                echo "Static website project - no compilation required"
                '''
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
