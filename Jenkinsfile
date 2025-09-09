@Library('Jenkins-shared-lib') _

pipeline{
    agent {label "agent-1"}
    stages{
        stage("Code"){
            steps{
                script{
                    clone()
                }
            }
        }
        stage("BUild"){
            steps{
                // echo "In this stage we are building the code"
                // sh "docker build -t notesapp ."
                // echo "Building the code successful"
                script{
                    build()
                }
            }
        }
        stage("Push"){
            steps{
                script{
                    credentialBinding()
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "In this stage we are deploying the app"
                sh "docker compose down && docker compose up -d "
            }
        }
    }
}
