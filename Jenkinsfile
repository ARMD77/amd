pipeline {
    agent {
        label "${Built-In-Node}"
           } 
      tools { 
      maven 'M2_HOME' 
      jdk 'JAVA_HOME' 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/*']], extensions: [], userRemoteConfigs: [[credentialsId: 'armd77', url: 'https://github.com/ARMD77/be.git']])
            }
        }
        stage('Package')  {
            steps {
                sh 'mvn package'    
            }
        }
    }
}
