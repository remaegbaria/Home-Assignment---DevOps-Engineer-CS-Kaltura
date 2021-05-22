
def now = new Date()
pipeline {
       agent {
        docker { image 'httpd:2.4' }
    }
    parameters {
    string(name: 'Name', defaultValue: '', description: 'What is your name?')
    string(name: 'firstPort', defaultValue: '', description: 'What is the first port?')
    text(name: 'secondPort', defaultValue: '', description: 'What is the second port?')
  }


    stages {

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
    
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
            sh '''
                #!/bin/bash
                echo "hello world"
            '''
                echo "Deploying....${params.Name}"
                echo "two....${params.firstPort}"
                echo "three....${params.secondPort}"
                echo "current time is ${now}"
            

            }

        }
    }
}
