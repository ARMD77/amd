pipeline {
    agent {
        label "${master}"
           } 
      tools { 
      maven 'M2_HOME' 
      jdk 'JAVA_HOME' 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout "scmGit(branches: [[name: '*/develop']], extensions: [], userRemoteConfigs: [[credentialsId: 'armduser', url: 'https://github.com/ARMD77/be.git']])"
            }
        }
        stage('Package')  {
            steps {
                sh 'mvn package'    
            }
        }
    }
}