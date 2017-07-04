pipeline
{
    stages
	{
		stage('cloneCode') 
		{
			node('master')
			steps
			{
				sh 'hostname'
				sh 'uname' 
				echo '---------------------------------------------'
				git credentialsId: 'hanjie0', url: 'file:///d:/02_Workspace/01_FromGitHub/Jenkins'
			}
		}
		stage('build')
		{
			node('master')
			steps
			{
				echo 'pre_check'
				echo 'Clean'
				echo 'modelImport'
				echo 'codeGenerate'
				echo 'codeCompile'
			}
		}

		stage('test')
		{
			node('master')
			{
				echo 'test'
			}
		}
		stage('archieve')
		{
			node('master')
			{
				archiveArtifacts '%workspace%\\results\\*'

			}
		}
		stage('deploy')
		{
			node('master')
			{
				echo 'deploy'    
			}
		}
	}
}