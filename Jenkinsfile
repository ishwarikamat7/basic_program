pipeline{
    agent any
    environment{
        DIRECTORY_PATH="Path to code Directory"
        TESTING_ENVIRONMENT="TEST Environment"
        PRODUCTION_ENVIRONMENT="PROD Environment"
    }
    stages{
        stage("Build"){
            steps{
                echo "Fetch the source code from the $DIRECTORY_PATH."
                echo "Build the code using MAVEN!"
            }
        }
        stage("Test"){
            steps{
                echo "JUnit Tests and Integration Tests started!"
                echo "JUnit Tests and Integration Tests completed!"
            }
        }
        stage("Code Analysis"){
            steps{
                echo "Quality of code is checked as per industry standards!"
            }
        }
        stage("Security Scan"){
            steps{
                echo "OWASP ZAP is used for Security Scan!"
            }
        }
        stage("Deploy to Staging"){
            steps{
                echo "Deploying the application to a staging server using AWS EC2 instance"
                sleep(time: 10, unit: 'SECONDS')
                echo "DEPLOYED"
            }
        }
        stage("Test on Staging Server"){
            steps{
                echo "JUnit Tests and Integration Tests on Staging server started!"
                echo "JUnit Tests and Integration Tests on Staging server completed!"
            }
        }
        stage("Deploy for Production"){
            steps{
                echo "Deploy the code to $PRODUCTION_ENVIRONMENT!"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                body: "The pipeline completed successfully. No issues detected.",
                recipientProviders: [[$class: 'DevelopersRecipientProvider']],
                to: "ishwarikmt7@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                body: "The pipeline failed. Please check the build logs for details.",
                recipientProviders: [[$class: 'DevelopersRecipientProvider']],
                to: "ishwarikmt7@gmail.com"
            )
        }
    }
}
