pipleline{
  agent {
    docker {
      image 'abhishekf5/maven-abhishek-docker-agent:v1'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' // mount Docker socket to access the host's Docker daemon
    }
  }

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


