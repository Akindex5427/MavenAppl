pipleline{
  agent any

  tools {
    jdk 'Java17'
    maven 'Maven3'
  }

  stages{
    stage ("Cleanup Workspace"){
      steps {
        cleanWs()
      }
    }

    stage("Checkout from SCM"){
      steps {
        git branch: 'master', credentials: 'github', url: 'https://github.com/Akindex5427/MavenAppl'
      }
    }

    stage("Build Application"){
      steps {
        sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps {
        sh "mvn test"
      }
    }
  }
}
