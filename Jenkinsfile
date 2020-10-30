pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f javademos/ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(artifacts: '**/target/*.war', fingerprint: true)
        sh '''mkdir /home/dushyanta/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/dushyanta/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}