node{

  def tomcatWeb = 'C:\\apache-tomcat-8.5.64\\webapps' 
  def mvnHome = tool name : 'maven-3',  type : 'maven'
  
  stage ('CheckOut') {
  	git 'https://github.com/jona987/webApp.git'
  }
  
  stage ('Build') {
  	bat "{mvnHome}/bin/mvn package"
  }
  
  /*stage ('Sonar Check') {
    withSonarQubeEnv('sonar-1'){
    	bat "{mvnHome}/bin/mvn sonar:sonar"
    }
  }*/
  
  stage ("Deploy") {
  	copy "target\\webApplication.war {tomcatWeb}\\webApplication.war"
  }
  
}