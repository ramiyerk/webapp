
node {
   stage('Checkout') {
   git 'https://github.com/anup03gupta/webapp.git'
    
}
stage('Build') {
   def mvnHome=tool name: 'apache-maven-3.5.4', type: 'maven'
 sh '${mvnHome}/bin/mvn package'

}
stage('Package') {
   sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war anup@172.31.31.71:/opt/apache-tomcat-9.0.11/webapps/'
}

}


}


