@Library('my-shared-library') _

pipeline{
    agent any

    stages{
        stage('Git Checkout') {
            steps{
                script{
                    gitCheckout{
                        branch: "main"
                        url: "https://github.com/rajan02l213/demo-counter-app.git"
                    }
                }
            }
        }
    }
}
