pipeline{
	agent any 
	tools{
		maven "maven3.9.1"
	}
	stages{
		stage('1GetCode'){
			steps{
				sh "echo 'Cloning the latest application version'"
				git credentialsId: 'github-cred', url: 'https://github.com/abrifuh6/maven-web-app'
			}
		}
		stage('2Test&Build'){
			steps{
				sh " echo 'Running JUnit-test-cases' "
				sh " echo 'Test cases must pass to build artifacts for deployment' "
				sh "mvn clean package"
			}
		}
		/*stage('3Sonarqube+CodeQuality'){
			steps{
				sh " echo 'Performing CodeQuality Analysis with SonarQube' "
				sh "mvn sonar:sonar"
			}
		}
		stage('4UploadArtifacts'){
			steps{
				sh " echo 'Uploading Built Artifacts to Nexus'"
				sh "mvn deploy"
			}
		}
		stage('5DeploytoProd'){
			steps{
				sh "echo 'Deploy application to tomcat prod-servers' "
			 deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://44.211.46.165:8080/')], contextPath: null, war: 'target/*war'
			}
		}*/
	}
	// options{}
	/*post{
		always{
			emailext body: '''Hello Guys,
Please check build status

Buamtech Consulting Inc.''', recipientProviders: [buildUser(), contributor(), upstreamDevelopers()], subject: 'Success'
		}
		success{
	      emailext body: '''Hello Guys,
 Great Job , Build and deployment Successful

Buamtech Consulting Inc.''', recipientProviders: [buildUser(), contributor(), upstreamDevelopers()], subject: 'Success'
		}
		failure{
	emailext body: '''Hello Guys,
 Build and deployment Failed, Please reslove Issue/Issues

Buamtech Consulting Inc.''', recipientProviders: [buildUser(), contributor(), upstreamDevelopers()], subject: 'Success'
		}
	}	*/
  }

