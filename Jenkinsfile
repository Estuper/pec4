properties([pipelineTriggers([githubPush()])])

node {
    git url: 'https://github.com/Estuper/pec4.git', branch: 'master'
}
pipeline {
tools {
maven "M3"
}
agent any
stages {
stage("Preparation") {
steps {
git 'https://github.com/Estuper/pec4.git'
}
}
stage("Test") {
steps {
script {

 sh "/home/estuper/Descargas/arachni-1.5.1-0.5.12/bin/arachni  http://192.168.3.210:81/vulnerabilities/exec/ --checks=**"

}
}
}
}
post {
always {
  archive "${BUILD_TAG}.afr"
  sh "arachni_reporter ${BUILD_TAG}.afr –reporter=xml:outfile=${BUILD_TAG}.xml"
    }
}
}