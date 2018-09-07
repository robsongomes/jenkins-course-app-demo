pipeline {
    def server = Artifactory.server('jfrog')
    def rtMaven = Artifactory.newMavenBuild()

    stage 'Build'
        git 'https://github.com/robsongomes/jenkins-course-app-demo.git' 

    stage 'Artifactory configuration'
        rtMaven.tool =  'maven'
        rtMaven.resolver server: server, releaseRepo: 'libs-release', snapshotRepo: 'libs-snapshot' 
        rtMaven.deployer server: server, releaseRepo: 'libs-release-local', snapshotRepo: 'libs-snapshot-local'
        def buildInfo = Artifactory.newBuildInfo()
        rtMaven.run pom: 'pom.xml', goals: 'clean package', buildInfo: buildInfo
        server.publishBuildInfo buildInfo
}