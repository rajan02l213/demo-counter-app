@Library('my-shared-library') _

pipeline{
    agent any

    stages{
        stage('Git Checkout') {
            steps{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/rajan02l213/demo-counter-app.git"
                    )
            }
        }
        stage('Unit Test') {
            steps{
                    script{
                        mvnTest()
                    )
            }
        }        
    }
}
