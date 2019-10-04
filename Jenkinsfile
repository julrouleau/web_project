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
		post {
			success{
				echo 'now archiving'
				archiveArtifacts artifacts: '**/target/*.war'
			}
		}
		stage('deploy'){
                        steps{
                        deploy adapters: [tomcat9(credentialsId: 'bce9860a-9996-43ad-9576-def09b620eef', path: '', url: 'http://localhost:8280')], contextPath: '/web2', onFailure: false, war: '**/*.war'
			}
                }
	}
}
