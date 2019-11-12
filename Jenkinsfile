properties([pipelineTriggers([pollSCM('H/3 * * * *')])])
node(){
	cleanWs()
	checkout scm
	stages{
		stage('Build'){
			steps{
				sh "make"
			}
		}
		stage('Test'){
			steps{
				sh "./main"
			}
		}
		stage('Archive'){
			steps{
				archiveArtifacts(artifacts: 'main, *.o', fingerprint: true, onlyIfSuccessful: true)
			}
		}
	}
}
			
