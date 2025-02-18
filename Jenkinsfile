pipeline {
    agent any
    
    stages {
        stage("Fetch Code") {
            steps {
                git branch: 'main', url: 'https://github.com/Kamalpreetgulati118/jenkins-demo.git'
            }
        }
        
        stage("Install Webserver") {
            steps {
                sh '''
                    sudo apt update 
                    sudo apt install -y apache2
                    sudo systemctl start apache2
                    sudo systemctl enable apache2
                '''
            }
        }
        
        stage("Deploy App") {
            steps {
                sh '''
                    sudo cp -R * /var/www/html/
                    sudo systemctl restart apache2
                '''
            }
        }
    }
}
