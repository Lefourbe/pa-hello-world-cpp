properties([pipelineTriggers([pollSCM('H/3 * * * *')])])
node(){
	cleanWs()
	checkout scm
	sh "make"
	sh "./main"
	archiveArtifact(allowEmptyArchive: false, artifacts: 'build/*', fingerprint: true, onlyIfSuccessful: true)
}
