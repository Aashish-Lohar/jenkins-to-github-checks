pipeline {
    agent any

    stages {
        stage('first') {
            steps {
                echo 'Hello World Testing'
            }
        }
        
        // stage('second') {
        //     steps {
        //         script{
        //             publishChecks name: 'test-publish-checks', 
        //             summary: 'testing summary', 
        //             text: 'test-publish-checks-text', 
        //             title: 'test-publish-checks-title'
        //         }
        //     }
        // }
        // stage('third') {
        //     steps {
        //         script{
        //             publishChecks annotations: [[endLine: 10, message: 'annotation message', path: 'Jenkinsfile', rawDetails: 'raw details', startLine: 5, title: 'test annotation']],  
        //             name: 'testing annotations', 
        //             summary: 'summary', 
        //             text: 'text', 
        //             title: 'title'
        //         }
        //     }
        // }
    }
}