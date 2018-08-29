node {
    stage('SCM checkout') {
    git 'https://github.com/anup03gupta/webapp.git'

}
stage('Build') {
	def mvn_version= 'maven'
   withEnv(['PATH+MAVEN=${tool mvn_version}/bin']) {
    sh 'mvn clean package'
}

}
stage('Deploy') {
	sshagent(['pipe']) {
		sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.36.70:/var/lib/tomacat8/webapps/'	
 
	}	
}



}
