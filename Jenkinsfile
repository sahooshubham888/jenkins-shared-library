@Library('library-test') _

pipeline{
	agent any
	stages{
	   stage('checkout'){
	       steps{
	           helloWorld()
	       }
	   }
	   stage ('build using maven'){
	       steps {
	           mavenBuild()
	       }
	   }
	   stages {
           stage("Tools initialization") {
               steps {
                   "mvn --version"
                   "java -version"
               }
           }
		   }
//            stage("Cleaning workspace") {
//                steps {
//                    sh "mvn clean"
//                }
// 			    }
//            stage("Running Testcase") {
//               steps {
//                    sh "mvn test"
//                }
//            }
// 		   stage("Packing Application") {
//                steps {
//                    sh "mvn package -DskipTests"
//                }
//            }
// 	}
}