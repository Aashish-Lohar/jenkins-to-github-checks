pipeline {
    agent any

    stages {
        stage('first') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('second') {
            steps {
                script{
                    publishChecks name: 'test-publish-checks', 
                    summary: 'testing summary', 
                    text: 'test-publish-checks-text', 
                    title: 'test-publish-checks-title'
                }
            }
        }
    }
}
