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
            post{
                always{
                    mail to: "khuzaima.Jamil@gmail.com",
                    subject: "JUnit integration test",
                    body: "Status: completed"
                }
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
            post{
                always{
                    mail to: "khuzaima.Jamil@gmail.com",
                    subject: "OWASP ZAP Security test",
                    body: "Status: completed"
                }
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
                    mail to: "khuzaima.Jamil@gmail.com",
                    subject: "Pipieline run completed",
                    body: "Status: completed. Build log: http://localhost:8080/job/pipeline%206.2/2/consoleText",
                    attachLog: true
        }
    }
}
