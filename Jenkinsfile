pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git branch: 'main', url:'https://github.com/1234shaik/aws-elastic-beanstalk-express-js-sample.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('npm Build') {
            steps {
                bat 'npm pack'
            }
        }
       
    }
}
       
        
