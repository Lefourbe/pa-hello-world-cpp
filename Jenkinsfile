properties([pipelineTriggers([pollSCM('H/3 * * * *')])])
node(){
	cleanWs()
	checkout scm
	sh "make"
	sh "./main"
	archiveArtifacts(allowEmptyArchive: false, artifacts: 'main, main.o', fingerprint: true, onlyIfSuccessful: true)
}
