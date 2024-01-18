node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
      sh '''
mvn clean verify sonar:sonar \
  -Dsonar.projectKey=SBA_Backend_Code1 \
  -Dsonar.projectName='SBA_Backend_Code1' \
  -Dsonar.host.url=http://3.111.149.70:9000 \
  -Dsonar.token=sqp_f09afa17da34b3b480b705463d1d184d54865497
  '''
    }
  }
}
