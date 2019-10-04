pipeline{
	agent any
	stages{
		stage('build'){
			steps{
				bat 'mvn clean package'
			}
		}
		post {
			success{
				echo 'now archiving'
				archiveArtifacts artifacts: '**/target/*.war'
			}
		}
	}
}
