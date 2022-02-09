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

    post {
     // send email notification the specicied addresses if the build fails
      failure {  
             mail bcc: '', body: "<b>Failed Jenkins Build</b><br>Project: ${env.JOB_NAME} 
             <br>Build Number: ${env.BUILD_NUMBER} <br> URL of the build: ${env.BUILD_URL}", cc: '', 
             charset: 'UTF-8', from: 'jenkins@jenkins-build.com', mimeType: 'text/html', replyTo: 'put@youremail.com', 
             subject: "ERROR CI: Project name -> ${env.JOB_NAME}", 
             to: "daresoremi@gmail.com";  
         }
    }
}
