pipeline {
    agent any
   
    stages {
        stage('permission') {
            steps {
                echo 'Building...'
                sh 'chmod +x ./script.sh'
            }
        }
       
        stage('execute') {
            steps {
                echo 'Testing...'
            }
        }
       
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh './script.sh'
            }
        }
    }
   
    post {
       
       
        success {
            echo 'This will run only if the pipeline succeeds.'
        }
       
        failure {
            echo 'This will run only if the pipeline fails.'
        }

        always {
            emailext (
                subject: 'Pipeline status is good',
                body: 'Pipeline is successfully executed',
                to: 'sarareddy02@gmail.com',
                from: 'sarareddy02@gmail.com',
                replyTo: 'govardhang@gmail.com',
                mimeType: 'text/html'
            )
        }
    }
}

