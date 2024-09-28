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
                withChecks(includeStage: true, name: 'test1') {
                        echo 'inside with checks'
                        sh "curl google.com"
                    }

                }
            }
        }
        stage('third') {
            steps {
                script{
                publishChecks name: 'test-publish-checks', summary: 'testing summary', text: 'test-publish-checks-text', title: 'test-publish-checks-title'

                }
            }
        }
        stage('fourth') {
            steps {
                script{
                withChecks(includeStage: true, name: 'test1') {
                        echo 'inside with checks and publish checks'
                        publishChecks name: 'test-publish-checks', summary: 'testing summary', text: 'test-publish-checks-text', title: 'test-publish-checks-title'
                    }
                    publishChecks name: 'test1', summary: 'testing summary', text: 'test1-publish-checks-text', title: 'test1-publish-checks-title'
                }
            }
        }
    }
}
