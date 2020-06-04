pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'php --version'
                bat 'composer install'
                bat 'php artisan key:generate'
            }
        }
        stage('test') {
            steps {
                bat 'vendor/bin/phpunit' 
              
        }
    }
    }
}
