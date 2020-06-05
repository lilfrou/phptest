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
              /*  step([
$class: 'CloverPublisher',
cloverReportDir: 'reports/coverage',
cloverReportFileName: 'coverage.xml',
healthyTarget: [methodCoverage: 70, conditionalCoverage: 80, statementCoverage: 80],
unhealthyTarget: [methodCoverage: 50, conditionalCoverage: 50, statementCoverage: 50],
failingTarget: [methodCoverage: 0, conditionalCoverage: 0, statementCoverage: 0]]) */
              
        }
              post {
        always {
             script {   
                                   
                                    
            //junit 'visamane-admin-backend-web/target/surefire-reports/*.xml'
            //step([$class: 'Publisher', reportFilenamePattern: '**/coverage.xml'])
                       step([
$class: 'CloverPublisher',
cloverReportDir: 'reports/coverage',
cloverReportFileName: 'coverage.xml',
healthyTarget: [methodCoverage: 70, conditionalCoverage: 80, statementCoverage: 80],
unhealthyTarget: [methodCoverage: 50, conditionalCoverage: 50, statementCoverage: 50],
failingTarget: [methodCoverage: 0, conditionalCoverage: 0, statementCoverage: 0]]) 
                                    
             }
        }
    }
          
    }
    }
}
