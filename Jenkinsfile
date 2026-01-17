pipeline {
  agent any
  stages {
    stage('Docker Build') {
      steps {
        sh 'docker build -t rhohith2001/gonemad:latest .'
      }
    }
    stage('Docker Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'docker', passwordVariable: '3D*T*arHVpjy/4X', usernameVariable: 'rhohith2001')]) {
          sh "docker login -u ${env.dockerUser} -p ${env.dockerPassword}"
          sh 'docker push rhohith2001/gonemad:latest'
        }
      }
    }
  }
}
