pipeline {
    agent any

    stages {
        stage('Fetch Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Kamalpreetgulati118/jenkins-demo.git'
            }
        }

        stage('Install webserver') {
            steps {
                sh ''' 
                sudo apt update
                sudo apt install apache2 -y
                '''
            }
        }

        stage('Deploy application') {
            steps {
                sh 'sudo cp -R * /var/www/html/'
            }
        }
    }
}
