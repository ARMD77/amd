node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
      sh '''
      sonar-scanner \
  -Dsonar.projectKey=SBA_Backend_Code1 \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://3.111.149.70:9000 \
  -Dsonar.token=sqp_89dad721e1995fdf74e60096167fe75ec782d244
  '''
    }
  }
}
