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
	stage("CreateInstance"){
	withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'b7bb5e0e-017e-45bf-b639-a2cde0d50dc5', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) 
		{	
			aws ec2 run-instances --image-id ami-2871f652 --count 1 --instance-type t2.micro --key-name mano665class --security-group-ids sg-0cb733d8ddff94802 --subnet-id subnet-018844073869cc7ba region us-east-1
		}	
	}
}
