pipeline{
    agent any
    tools {nodejs "Nodejs"}
    stages {
        stage('Clone Repository'){
            steps{
                git branch: 'main', credentialsId: 'github-login', url: 'https://github.com/himansh14/express_server_for_flutter_app_testing.git'
            }
        }
        stage('Install Dependencies'){
            steps {
                sh 'npm install'
            }
        }
         stage('Install pm2'){
            steps {
                sh 'npm install pm2 -g'
            }
        }
        stage('Deploy'){
            steps {
                sh 'pm2 startOrRestart pm2.config.json'
            }
        }
    }
}
