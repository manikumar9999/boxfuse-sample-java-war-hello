pipeline {
  agent any
  tools {
     maven 'maven3.6.3'
          }
       stages{
          stage('Build'){
             steps{
             sh script: 'mvn clean package'
          }
        }
         stage('Upload War To Nexus'){
             steps{
                nexusArtifactUploader artifacts: [
                   [
                    artifactId: 'simple-app',
                    classifier: '',
                    file: 'target/simple-app-1.0.war',
                    type: 'war'
                  ]
              ],
 credentialsId: 'mani123',
 groupId: 'com.boxfuse.samples',
 nexusUrl: '172.31.39.68:8081',
 nexusVersion: 'nexus3',
 protocol: 'http',
 repository: 'simpleapp-release',
 version: '1.0'
}
}
}
}
