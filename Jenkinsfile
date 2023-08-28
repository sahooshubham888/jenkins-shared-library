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

myDeliveryPipeline(branch: 'main', scmUrl: 'ssh://git@github.com:sahooshubham888/jenkins-shared-library.git',
                   email: 'team@example.com', serverPort: '8080',
                   developmentServer: 'dev-myproject.echo.com',
                   stagingServer: 'staging-myproject.echo.com',
                   productionServer: 'production-myproject.echo.com')