@Library('library-test') _

pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
            gitCheckout(
                branch: "main",
                url: "https://github.com/sahooshubham888/jenkins-shared-library.git"
            )
            }
    }
    }
}
