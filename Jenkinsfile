@Library('library-test') _

pipeline {
      stages{
          stage('checkout'){
              steps{
                 helloWorld()
            }
        }   
    }
    stages {
        stage("Tools initialization") {
            steps {
                   sh "mvn --version"
                   sh "java -version"
            }
        }
    }
    stage("Cleaning workspace") {
        steps {
               sh "mvn clean"
            }
        }
    }
    stage("Running Testcase") {
          steps {
               sh "mvn test"
            }
        }
    }
    stage("Packing Application") {
          steps {
               sh "mvn package -DskipTests"
            }
        }
    }
}
