@Library('my-shared-library') _

pipeline{
    agent any
    parameters{
        choice(name: 'action',choices: 'create\n delete', description: 'choose create/destroy')
    }
    stages{
        stage('Git Checkout') {
        when{ expression { params.action == 'create'}}
            
            steps{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/rajan02l213/demo-counter-app.git"
                    )
            }
        }
        stage('Unit Test') {
        when{ expression { params.action == 'create'}}
            
            steps{
                    script{
                        mvnTest()
                    }
            }
        }
        stage('Integration Test') {
        when{ expression { params.action == 'create'}}
            
            steps{
                    script{
                        mvnIntegrationTest()
                    }
            }
        }     
        stage('Static Code Analysis Sonar Test') {
        when{ expression { params.action == 'create'}}
            
            steps{
                    script{
                        def sonarQubeId = 'sonar-id'
                        
                        staticCode(sonarQubeId)
                    }
            }
        }         
    }
}
