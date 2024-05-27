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
         stage('SonarQube Analysis') {
             environment {
                sonar_user = credentials('sonar_user')
            }
            steps {
               bat ''' sonar-scanner.bat 
                -D"sonar.projectKey=npm_project" 
                -D"sonar.sources=." 
                -D"sonar.host.url=http://localhost:9000" ,
                -D"sonar.token=%sonar_user%
                // -D"sonar.token=sqp_a8ef086bb2cf587626730ea184f91af4534d967d" '''
                   }
                }
    }
}
       
        
