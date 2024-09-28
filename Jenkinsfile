pipeline {
    agent any

    stages {
        stage('first') {
            steps {
                echo 'Hello World Testing'
            }
        }
        
        stage('second') {
            steps {
                script{
                    // command is a variable where you can store a command as a string, allowing you to execute it in a pipeline step at a later stage.
                    def command = "curl google.com"
                    sh(script: "echo '## + $command' >> logsfile.txt")
                    def status = sh(returnStatus: true, script: "$command > command_output.txt")
                    def output = sh(returnStdout: true, script: "cat command_output.txt")
                    sh(script: "echo '```\n$output```\n' >> logsfile.txt")

                    def logsToPublish = sh(returnStdout: true, script: "cat logsfile.txt")
                    publishChecks name: 'custom-checks', 
                    summary: 'custom-checks summary', 
                    text: logsToPublish, 
                    title: 'custom-checks-title'
                }
            }
        }
        stage('third') {
            steps {
                script{
                    // command is a variable where you can store a command as a string, allowing you to execute it in a pipeline step at a later stage.
                    def command = "ping -c 4 google.com"
                    sh(script: "echo '## + $command' >> logsfile.txt")
                    status = sh(returnStatus: true, script: "$command > command_output.txt")
                    output = sh(returnStdout: true, script: "cat command_output.txt")
                    sh(script: "echo '```\n$output```\n' >> logsfile.txt")
                    
                    logsToPublish = sh(returnStdout: true, script: "cat logsfile.txt")
                    publishChecks name: 'custom-checks', 
                    summary: 'custom-checks summary', 
                    text: logsToPublish, 
                    title: 'custom-checks-title'
                }
            }
        }
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