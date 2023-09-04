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
	}
}