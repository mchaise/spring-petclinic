pipeline {
    agent any
     triggers { pollSCM('*/3 * * * *') }
    stages {
        stage('download source code') {
            
            steps {
                git branch: 'main', url: 'https://github.com/shivakumarkokomuravelly/spring-petclinic.git'
            }
        }
        stage('Creating Artifacts') {
             
            steps {
                sh 'mvn package'
            }
        }
       stage('archiving artifacts'){
         steps{
                 archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
   }
}   
  stage('displaying unit test reports'){
   steps{                
        junit 'target/surefire-reports/*.xml'
    }
}

}
}
