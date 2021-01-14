podTemplate(yaml: '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: maven
    image: maven:3.6.3-jdk-8
    command:
    - sleep
    args:
    - infinity
''') {
  node(POD_LABEL) {
    checkout scm
    container('maven') {
      sh 'pwd'
      sh 'ls -la'
      sh 'mvn -B -Dmaven.test.failure.ignore clean compile package'
    }
    junit '**/target/surefire-reports/TEST-*.xml'
  }
}
