pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '"C:\Users\User\AppData\Local\Jenkins\.jenkins\workspace\UchePipeline"'
        TESTING_ENVIRONMENT = 'Test'
        PRODUCTION_ENVIRONMENT = 'Uche'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Fetching source code from the directory path specified by the environment variable: ${DIRECTORY_PATH}'
            }

            stage('Compile and Generate Artifacts') {
                steps {
                    echo 'Compile the code and generate any necessary artifacts'
                }
            }

            stage('Test') {
                steps {
                    echo 'Running unit tests'
                    echo 'Running integration tests'
                }
            }

            stage('Code Quality Check') {
                steps {
                    echo 'Checking the quality of the code'
                }
            }

            stage('Deploy') {
                steps {
                    echo 'Deploying the application to a testing environment specified by the environment variable: ${TESTING_ENVIRONMENT}'
                }
            }

            stage('Approval') {
                steps {
                    echo 'Waitig for manual approval'
                    sleep 10
                }
            }

            stage('Deploy to Production') {
                when {
                    environment name: 'PRODUCTION_ENVIRONMENT', value: 'Uche'
                }

                steps {
                    echo 'Deploying the application to the production environment specified by the environment variable: ${PRODUCTION_ENVIRONMENT}'
                }
            }
        }   
    
    }
}
