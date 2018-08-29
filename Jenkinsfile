
node {
   stage('Checkout') {
   git 'https://github.com/anup03gupta/webapp.git'
    
}
stage('Build') {
   def mvn_version = 'maven'	
 	withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {	
 	sh "mvn clean package"	 

   }
}
stage('Package') {
   sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war anup@172.31.31.71:/opt/apache-tomcat-9.0.11/webapps/'
}

}


}


