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
                bat "php vendor/phpunit/phpunit/phpunit --log-junit 'reports/unitreport.xml' --coverage-html 'reports/coverage' --coverage-clover 'reports/coverage/coverage.xml'"
              
        }
    }
    }
}
