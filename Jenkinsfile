node {
  stage('========== Clone repository ==========') {
    checkout scm
  }
  stage('========== Build image ==========') {
    app = docker.build("mhemperor/jenkins_test")
  }
  stage('========== Push image ==========') {
    docker.withRegistry('https://registry.hub.docker.com', 'mhemperor') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
}
