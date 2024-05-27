pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'This is test file'
            }
        }
        
        stage('Prod') {
            steps {
             sh'''
                ls 
                pwd
                touch test.txt
                ls -ltrh
                
                '''
            }
        }
        
        stage('ENV') {
            steps {
                sh 'echo "this is id ${BUILD_ID}'
                sh 'echo "this is URL" ${BUILD_URL}'
            }
        }
    }
}
