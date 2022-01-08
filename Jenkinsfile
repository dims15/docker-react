pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                echo "========executing Checkout========"
                git credentialsId: '7ddad5d7-5f03-4b32-8b02-afa48929d442', url: 'https://github.com/dims15/docker-react.git'
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
                script{
                    docker.build("dimasandriyan:frontend", "-f Dockerfile.dev .")    
                }                
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