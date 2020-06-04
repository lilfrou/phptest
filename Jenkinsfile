pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'php --version'
                bat 'composer install'
            }
        }
        stage('test') {
            steps {
                bat 'vendor/bin/phpunit' 
              
        }
    }
}
