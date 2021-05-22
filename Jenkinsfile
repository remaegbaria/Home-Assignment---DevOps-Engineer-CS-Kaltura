def currentTime
def now = new Date()
pipeline {
    //  agent any
       agent {
        docker { image 'httpd:httpd:2.4' }
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
        //  sh '''
        //     #!/bin/bash
        //     echo "hello world"
        //     docker run -u -dit --name my-apache-app -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4
           
        //  '''
            //  script {
            //                 sudo apt update
            // sudo apt install docker.io
            // sudo docker run -dit --name my-apache-app -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4
            // sudo docker ps
             // httpd --version
                
            //     }
                // sh "echo ${currentTime}"
                echo "Deploying....${params.Name}"
                echo "two....${params.firstPort}"
                echo "three....${params.secondPort}"
                echo "current time is ${now}"
            }
        }
    }
}
