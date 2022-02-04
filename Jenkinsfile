pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building your code'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing your code'
            }
        }

        stage('Deploy to staging/QA') {
            steps {
                echo 'Deploying your code to staging/QA'
            }
        }

        stage('Deploy to prod') {
            input {
                message "Should we continue?"
                ok "Yes please"  
            }
            
            steps {
                echo 'Deploying your code to production'
            }
        }
    }
}
