@Library('library-test') _

pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
               git branch: "main",
                credentialsId: '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',
                url: "https://github.com/sahooshubham888/jenkins-shared-library.git"
            }
    }
    }
}

pipeline {
    agent any
    environment {
        branch = 'main'
        scmUrl = 'ssh://git@myScmServer.com/repos/'https://github.com/sahooshubham888/jenkins-shared-library.git'
        serverPort = '8080'
        developmentServer = 'dev-myproject.echo.com'
        stagingServer = 'staging-myproject.echo.com'
        productionServer = 'production-myproject.echo.com'
    }
    stages {
        stage('checkout git') {
            steps {
                git branch: main, credentialsId: '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', url: scmUrl
            }
        }

        stage('build') {
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage ('test') {
            steps {
                parallel (
                    "unit tests": { sh 'mvn test' },
                    "integration tests": { sh 'mvn integration-test' }
                )
            }
        }

        stage('deploy development'){
            steps {
                deploy(developmentServer, serverPort)
            }
        }

        stage('deploy staging'){
            steps {
                deploy(stagingServer, serverPort)
            }
        }

        stage('deploy production'){
            steps {
                deploy(productionServer, serverPort)
            }
        }
    }
    post {
        failure {
            mail to: 'team@example.com', subject: 'Pipeline failed', body: "${env.BUILD_URL}"
        }
    }
}

myDeliveryPipeline(branch: 'main', scmUrl: 'ssh://git@myScmServer.com/repos/https://github.com/sahooshubham888/jenkins-shared-library.git',
                   email: 'team@example.com', serverPort: '8080',
                   developmentServer: 'dev-myproject.echo.com',
                   stagingServer: 'staging-myproject.echo.com',
                   productionServer: 'production-myproject.echo.com')


myDeliveryPipeline {
    branch = 'main'
    scmUrl = 'ssh://git@myScmServer.com/repos/https://github.com/sahooshubham888/jenkins-shared-library.git'
    email = 'team@example.com'
    serverPort = '8080'
    developmentServer = 'dev-myproject.echo.com'
    stagingServer = 'staging-myproject.echo.com'
    productionServer = 'production-myproject.echo.com'
}
