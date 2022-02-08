pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building your code'
                // composer install # php
                // pip install -r requirements.txt # python
                // npm install # nodejs
                sh 'chmod +x test.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing your code'
                sh './test.sh'
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
                ok "Please do"  
            }
            
            steps {
                echo 'Deploying your code to production'
            }
        }
    }
}
