pipeline{
    agent{
        label "node"
    }
    environment{
        DIRECTORY_PATH="computer/source"
        TESTING_ENVIRONMENT="TESTING ENVIRONMENT"
        PRODUCTION_ENVIRONMENT="Khuzaima Jamil"

    }
    stages{
        stage("Build"){
            steps{
                echo "Maven used for build"
                echo "Compile code and generate any necessary build artifacts"
            }
        }
        stage("Test"){
            steps{
                echo "Junit integration tests"
            }
        }
        stage("Code Quality Check"){
            steps{
                echo "SonarQube code analysis and quality check"
            }
        }
       stage("Security test"){
            steps{
                echo "OWASP ZAP Security test"
            }
        }
        stage("Deploy to stage"){
            steps{
                echo "Deploying the application to stage AWS EC2"
            }
        }
        stage("Stage Test"){
            steps{
                echo "Stage Test Junit"
                sleep 10 // Sleep for 10 seconds
            }
        }
        stage("Deploy to prod"){
            steps{
                echo "Deploying the application to stage AWS EC2"
            }
        }
    }
    post { 
        always { 
                        emailext attachLog: true,
                        compressLog: true,
                        body: "Status: completed. test",
                        subject: "Pipieline run completed",
                        to: 'khuzaima.Jamil@gmail.com'
        }
    }
}
