pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */

agent {
    docker {
      image 'gradle:7.0.2-jdk11'
    }
  }

  stages {
    stage('Checkout') {
      steps {
        checkout(scm)
      }
    }

    stage('Build') {
      steps {
        // sh 'gradle clean build'
        ./gradlew assemble
      }
    }

    stage('Test') {
      steps {
        // sh 'gradle test'
        ./gradlew test
      }
    }

    // stage('Deploy') {
    //   steps {
    //     sh 'gradle deploy'
    //   }
    // }
  }

  triggers {
    githubPush()
  }
}
