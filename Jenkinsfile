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
        stage("Build image"){
            steps{
                echo "========executing Build image========"
                powershell 'docker build -f Dockerfile.dev -t dimasandriyan/frontend .'
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========Build image executed successfully========"
                }
                failure{
                    echo "========Build image execution failed========"
                }
            }
        }
    }
}