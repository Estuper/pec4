properties([pipelineTriggers([githubPush()])])

node {
    git url: 'https://github.com/Estuper/pec4.git', branch: 'master'
}

 pipeline {
        agent any
        stages {
            stage('Test') {
                steps {
                    echo 'Hello World ...'
                }
            }
        }
    }