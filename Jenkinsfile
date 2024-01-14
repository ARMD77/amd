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
  -Dsonar.host.url=http://43.205.214.173:9000 \
  -Dsonar.token=sqp_06bf73b8c1dc9fc122ad0ac091ffb92e589e93fd  
    '''
    }
    stage('Quality Gate') {
      steps {
        timeout (time: 4 , unit: 'MINUTES') {
          waitForQualityGate  abortPipeline: true
        }
      }
    }
  }
}
