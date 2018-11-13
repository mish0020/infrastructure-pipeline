properties([pipelineTriggers([githubPush()])])

node('linux'){
    git url: 'https://github.com/mish0020/infrastructure-pipeline.git',
	branch : 'master'
	stage('Test'){
		sh "env"
	}
}	
