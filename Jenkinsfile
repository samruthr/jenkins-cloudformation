/*pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
                withAWS(region: 'us-west-2', credentials: 'treebeard') {
                    def outputs = cfnUpdate(stack:'JenkinsPipelineTest', file:'templates/vpc.yaml', params:['VPCName=JenkinsPipelineTest'], timeoutInMinutes:10, tags:['TagName=JenkinsPipelineTest'], pollInterval:1000)
                    echo "${outputs}"
                }
            }
        }
    }
}*/

node {
    stage('checkout') {
        checkout scm
    }
    stage('deploy') {
        withAWS(region: 'us-west-2', credentials: 'treebeard') {
        def outputs = cfnUpdate(stack:'JenkinsPipelineTest', file:'templates/vpc.yaml', params:['VPCName=JenkinsPipelineTest'], timeoutInMinutes:10, tags:['TagName=JenkinsPipelineTest'], pollInterval:1000)
        echo "${outputs}"
        }
    }
}