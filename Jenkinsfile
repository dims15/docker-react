pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                echo "========executing Checkout========"
                git credentialsId: 'd328bd89-83d2-4b9a-917e-e9cd613222c1', url: 'https://github.com/dims15/docker-react.git'
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========Checkout executed successfully========"
                }
                failure{
                    echo "========Checkout execution failed========"
                }
            }
        }
    }
}