apiVersion: v1
kind: BuildConfig
metadata:
annotations:
pipeline.alpha.openshift.io/uses: '[{"name": "nodejs-example", "namespace": "development",
"kind": "DeploymentConfig"}]'
creationTimestamp: 2016-12-22T13:54:23Z
labels:
app: jenkins-pipeline-development
name: development-pipeline
template: application-template-development-pipeline
name: development-pipeline
namespace: jenkins
resourceVersion: "5781"
selfLink: /oapi/v1/namespaces/jenkins/buildconfigs/development-pipeline
uid: 24c166c2-c84e-11e6-b4f7-68f7286606f4
spec:
output: {}
postCommit: {}
resources: {}
runPolicy: Serial
source:
type: None
strategy:
jenkinsPipelineStrategy:
jenkinsfile: |-
node('maven') {
stage 'build'
openshiftBuild(buildConfig: 'nodejs-example', showBuildLogs: 'true', namespace: 'development')
stage 'deploy'
openshiftDeploy(deploymentConfig: 'nodejs-example', namespace: 'development')
}
type: JenkinsPipeline