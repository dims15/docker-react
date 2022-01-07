pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                echo "========executing Checkout========"
                git credentialsId: '8446e77e-2391-479c-b243-e18c824d7b5f', url: 'https://github.com/dims15/docker-react.git'
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

                docker.build("dimasandriyan:frontend", "-f Dockerfile.dev .")
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