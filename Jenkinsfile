pipeline {
    parameters{
       string defaultValue: 'testValue', name: 'testArg' 
    }
    
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'HelloWorld'
                sh 'echo ${testArg}'
                sh 'echo "Added from snippet generator"'
            }
        }
          
        stage('Execute shell') {
            
            agent {
                label 'built-in'
            
            }
            
            steps {
                sh 'ls'
                sh 'chmod +x HelloWorld.sh'
                sh './HelloWorld.sh'
            }
        }
        
        stage ('clean WS'){
            steps {
                cleanWs()
            }
        }
        
    }
    
}
