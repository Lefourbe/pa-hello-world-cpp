properties([pipelineTriggers([pollSCM('H/3 * * * *')])])
node(){
	docker.image('gcc:4.9').inside{
		cleanWs()
		checkout scm
		stage('Build'){
			sh "make"
		}
		stage('Test'){
			sh "./main"
		}
		stage('Archive'){
			archiveArtifacts(artifacts: 'main, *.o', fingerprint: true, onlyIfSuccessful: true)
		}
	}
}
			
