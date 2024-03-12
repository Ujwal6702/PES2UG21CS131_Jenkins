pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output PES2UG21CS131-1.cpp'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }
    }
    
    post {
        always {
            script {
                currentBuild.result = currentBuild.result ?: 'SUCCESS'
                if (currentBuild.result == 'FAILURE') {
                    echo 'Pipeline failed'
                }
            }
        }
    }
}
