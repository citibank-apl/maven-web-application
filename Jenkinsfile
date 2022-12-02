node{
    def mavenHome = tool name : 'maven3.8.5'
echo "The job name is: ${env.JOB_NAME}"
echo "The Build number is: ${env.BUILD_NUMBER}"
echo "The Node name is: ${env.NODE_NAME}"

//checkout code stage
stage('CheckoutCode'){
git branch: 'development', credentialsId: '564b40e7-fd78-4b8e-99bb-df3ff13654f9', url: 'https://github.com/citibank-apl/maven-web-application.git'
}
//Build
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}
  /*
//Execute SonarQube Report
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
//UploadArtifacts Into Nexus
stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}
//Deploy App into Tomcat Server
stage('DeployApp'){
sshagent(['07d5abe6-15a7-4ff0-ad84-838552cdd891']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.26.127:/opt/apache-tomcat-9.0.68/webapps/"
}
}
*/
  
}//node closing
