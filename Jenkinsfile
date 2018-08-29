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
	sh 'sudo cp target/*.war /var/lib/tomcat8/webapps/'	
	}	



}
