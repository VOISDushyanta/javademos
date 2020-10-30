pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f javademos/ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(artifacts: '**/target/*.war', fingerprint: true)
        sh '''mkdir /home/dushyanta/buildoutput/${BUILD_NUMBER}
cp /var/lib/jenkins/workspace/javademos_master/javademos/ssgsems/target/*.war /home/dushyanta/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}