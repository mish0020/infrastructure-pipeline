properties([pipelineTriggers([githubPush()])])

node('linux'){
    git url: 'https://github.com/mish0020/infrastructure-pipeline.git',
	branch : 'master'
	stage('Test'){
		sh "env"
	}
	stage("GetInstances"){
		withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'b7bb5e0e-017e-45bf-b639-a2cde0d50dc5', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) 
		{
 			sh "aws ec2 describe-instances --region us-east-1"
                }		

	}		
}
