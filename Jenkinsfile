pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                // Example: Using JUnit for unit tests
                echo 'Running integration tests...'
                // Example: Using Selenium for integration tests
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Example: Using SonarQube for code analysis
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example: Using OWASP ZAP for security scan
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Example: Using Jenkins Deploy Plugin or AWS CLI for deployment
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example: Using Selenium for integration tests
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Example: Using Jenkins Deploy Plugin or AWS CLI for deployment
            }
        }
    }

    post {           
        success {
            emailext(
                subject: 'SUCCESS: Jenkins Pipeline',
                body: '''<html>
                            <body>
                         <p>The Pipeline build successful.</p>
                         <p> This is an update test</p>
                         <p>Check console output at <a href="${BUILD_URL}console">here</a> to view the full results.</p>
                            </body>
                          </html>''',
                to: 'justicevincent872@gmail.com',
                mimeType: 'text/html',
                attachLog: true
            )
        }
        failure {
            emailext(
                subject: 'FAILURE: Jenkins Pipeline',
                body: '''<html>
                            <body>
                             <p>The Pipeline has failed.</p>
                             <p>Please check logs</p>
                             <p>Check console output at <a href="${BUILD_URL}console">here</a> to view the full results.</p>
                            </body>
                          </html>''',
                to: 'justicevincent872@gmail.com',
                mimeType: 'text/html',
                attachLog: true
            )
        }
    }
}
