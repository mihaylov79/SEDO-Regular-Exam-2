pipeline{
    agent any

    stages{
        stage("Checkout repository"){
            steps{
                checkout scm
            }
            post{
                always{
                    echo "=== Operation Started..... ==="
                }
                success{
                    echo "===Operation Complete successfuly==="
                }
                failure{
                    echo "===Operation failed==="
                }
            }
        }

        stage("Restore Dependencies"){
            steps{
                sh 'dotnet restore'
            }
            post{
                always{
                    echo "=== Operation Started..... ==="
                }
                success{
                    echo "===Operation Complete successfuly==="
                }
                failure{
                    echo "===Operation failed==="
                }
            }
        }

        stage("Build  Application"){
            steps{
                sh 'dotnet build --no-restore'
            }
            post{
                always{
                    echo "Operation Started....."
                }
                success{
                    echo "===Operation Complete Successfully==="
                }
                failure{
                    echo "===Operation failed==="
                }
            }
            
        }

        stage("Executing Tests"){
            steps{
                sh 'dotnet test --no-build --verbosity normal'
            }
            post{
                always{
                    echo "Operation Started....."
                }
                success{
                    echo "====Operation Complete Successfully===="
                }
                failure{
                    echo "====Operation failed===="
                }
            }
        }



    }
    post{
        always{
            echo "========execiting pipeline....========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}