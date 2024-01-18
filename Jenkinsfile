node {
  stage('SCM') {
    checkout scm
   }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarqube';
    withSonarQubeEnv() {
      sh ''' mvn clean verify sonar:sonar \
  -Dsonar.projectKey=SBA_Backend_Code \
  -Dsonar.projectName='SBA_Backend_Code' \
  -Dsonar.host.url=http://3.111.149.70:9000 \
  -Dsonar.token=sqp_89dad721e1995fdf74e60096167fe75ec782d244  
    '''
    }
  }
}
