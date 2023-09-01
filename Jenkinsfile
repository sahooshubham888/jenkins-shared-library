@Library('library-test') _

pipeline{
	agent any
	stages{
	   stage('Deploy'){
	       steps{
	           DeliveryPipeline('Deploy')
	           deploy('Deploy')
	       }
	   }
	}
}
