#!groovy

def path = 'C:\\Windows\\Microsoft.NET\\Framework\\v4.0.30319\\MSBuild.exe'

pipeline
{
	agent any
	stages
	{
		stage('First')
		{
			steps
			{
				myStep "woop2"
				myStep()
	
				bat "$path jenkinsProj.sln /p:Configuration=Release /p:Platform=Win32"
			}
		}
	}
	post
	{
		always
		{
			step(
			[
				$class: 'WarningsPublisher', 
				canRunOnFailed: true, 
				consoleParsers: [
				[
					parserName: 'MSBuild'
				]]
			])	
		}
	}
}