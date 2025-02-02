pipeline {
    agent any  // Run on any available agent

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Example command to clone a git repository
                    git branch: 'main', url: 'https://github.com/borkar-shubham/Jenkins.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Example command to install dependencies
                    sh 'sudo apt-get update'
                    sh 'sudo apt-get install -y build-essential'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Example command to run tests
                    sh 'sudo chmod +x ./run_tests.sh'
                    sh 'sudo ./run_tests.sh'
                }
            }
        }

        // stage('Build Application') {
        //     steps {
        //         script {
        //             // Example command to build the application
        //             sh 'make build'
        //         }
        //     }
        // }

        // stage('Deploy') {
        //     steps {
        //         script {
        //             // Example command to deploy the application
        //             sh 'scp -r ./build user@yourserver:/path/to/deploy'
        //         }
        //     }
        // }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }

        failure {
            echo 'Build or deployment failed!'
        }
    }
}
