pipeline {
  agent { label 'kaniko' }
  stages {
    stage('Build with Kaniko') {
      steps {
        container(name: 'kaniko', shell: '/busybox/sh') {
          sh '''#!/busybox/sh
            echo "FROM jenkins/inbound-agent:latest" > Dockerfile
            /kaniko/executor --context `pwd` --no-push --tar-path `pwd`/testapp.tar
            ls -al
          '''
        }
      }
    }
    stage('Unpack container') {
      steps {
        sh '''tar xvf testapp.tar
            ls -al
        '''
      }
    }
  }
}
