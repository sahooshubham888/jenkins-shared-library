@Library('library-test') _

pipeline {
       agent any
    //    tools {
    //        maven 'Maven 3.5.0'
    //        jdk 'jdk8'
    //    }
       stages {
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

           stage("Tools initialization") {
               steps {
                   sh "mvn --version"
                   sh "java -version"
               }
           }
           stage("Checkout Code") {
               steps {
                   git branch: 'master',
                       url: "https://github.com/iamvickyav/spring-boot-data-H2-embedded.git"
               }
           }
           stage("Cleaning workspace") {
               steps {
                   sh "mvn clean"
               }
           }
           stage("Running Testcase") {
              steps {
                   sh "mvn test"
               }
           }
           stage("Packing Application") {
               steps {
                   sh "mvn package -DskipTests"
               }
           }
       }
 }
