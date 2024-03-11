pipleline{

  agent any

  stages{
    stage ("Cleanup WOrkspace"){
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


