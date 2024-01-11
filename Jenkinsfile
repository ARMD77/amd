pipeline {
    agent {
        Built-In-Node
           } 
      tools { 
      maven 'M2_HOME' 
      jdk 'JAVA_HOME' 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github_admin_armd77', url: 'https://github.com/ARMD77/be.git']])
            }
        }
        stage('Package')  {
            steps {
                sh 'mvn package'    
            }
        }
    }
}