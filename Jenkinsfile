pipeline {
    agent any

    stages {
        stage('Running') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    triggers {
        pollSCM('* * * * *')
    }

    post {
        success {
            notify('success')
        }
        failure {
            notify('failure')
        }
    }
}

def notify(status) {
    slackSend(message: "Message from Jenkins Pipeline")
}