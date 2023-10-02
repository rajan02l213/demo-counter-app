@Library('my-shared-library') _

pipeline{
    agent any
    parameters{
        choice(name: 'action',choices: 'create\n delete', description: 'choose create/destroy')
    }
    stages{
        when{ expression { param.action == 'create'}}
        stage('Git Checkout') {
            steps{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/rajan02l213/demo-counter-app.git"
                    )
            }
        }
        stage('Unit Test') {
        when{ expression { param.action == 'create'}}
            
            steps{
                    script{
                        mvnTest()
                    }
            }
        }
        stage('Integration Test') {
        when{ expression { param.action == 'create'}}
            
            steps{
                    script{
                        mvnIntegrationTest()
                    }
            }
        }        
    }
}
