pipeline{
	agent any
	stages{
		stage('init'){
                        steps{
                                echo "testing"
                        }
                }
		stage('build'){
			steps{
				bat 'mvn clean package'
			}
		}
		stage('deploy'){
                        steps{
                                echo "deploy"
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
