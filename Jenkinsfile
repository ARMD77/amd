pipeline {
    agent {
        label "${master}"
           } 
      tools { 
      maven 'M2_HOME' 
      jdk 'JAVA_HOME' 
    }
    stages {
        stage('Package')  {
            steps {
                sh 'mvn package'    
            }
        }
    }
}
