pipeline{
    agent any

    stages{
        stage('Git Checkout') {
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/vikash-kumar01/demo-counter-app.git'
                }
            }
        }
    }
}