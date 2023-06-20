pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps { sh 'npm ci'
                // 
            }
        }
        stage('Test') { 
            steps {
                sh 'npm run allure:clearData'
                sh 'npm run cy:testWithAllureReport'

                // 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'npm run allure:generateReport'
                allure(
                    results: [['allure-results']]
                )
                // 
            }
        }
    }
}