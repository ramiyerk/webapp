
node {	
 	stage('SCM Checkout') {	
 	git 'https://github.com/anup03gupta/webapp.git'	
 	 	
 	}	
 	stage('Build') {	
 	def mvn_version = 'Maven'	
 	withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {	
 	sh "mvn clean package"	
 	}	
 	}	
 	stage('Package-Deploy') {	
 	sshagent(['tomcat-deploy']) {	
 	sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.41.209:/var/lib/tomacat8/webapps/'	
 	}	
 	}	
 	 	
 	 	
 	 	
 	}	 
 

