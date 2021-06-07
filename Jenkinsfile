pipeline{
  agent any;
  stages{
    stage('maven'){
      steps{
        rtMavenRun (
          tool: 'mvn3',
          pom: 'pom.xml',
          goals: '-B -Dmaven.test.failure.ignore clean compile package',
          resolverId: 'artifactory',
          deployerId: 'artifactory',
          )
        }
    }
  }
}
