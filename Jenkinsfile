
def now = new Date()
pipeline {
    agent any
    //    agent {
    //     docker { image 'httpd:2.4' }
    // }
    parameters {
    string(name: 'Name', defaultValue: '', description: 'What is your name?')
    string(name: 'firstPort', defaultValue: '', description: 'What is the first port?')
    text(name: 'secondPort', defaultValue: '', description: 'What is the second port?')
  }


    stages {

        stage('Build') {
            agent { docker 'httpd:2.4' } 
            steps {
                echo 'Hello,apache'
                sh 'httpd --version'
            }
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
               // docker.image('maven:3.3.3-jdk-8').inside {
        // git '…your-sources…'
        // sh 'mvn -B clean install'
        // }
        //    sh 'docker build -t my-apache2 .'
            // docker.image('httpd:2.4').inside ("-p 9222:9222 --security-opt seccomp=$WORKSPACE/chrome.json") { 
        // sh label: 
        // 'Running npm test', 
        // script: '''
        // npm run test
        // '''
        //   }
            steps {
                // sh 'docker build -t my-apache2 .'
                // sh 'docker run -dit --name my-running-app -p 80:80 my-apache2'
         sh '''
            #!/bin/bash
            echo "hello world"
          '''

            //          node {
            // script   {          
            // git '…' // checks out Dockerfile & Makefile
            // def myAp = docker.build 'my-apache2'
            // myAp.inside {
            //     sh 'echo "hello"'
            // }
                echo "Deploying....${params.Name}"
                echo "two....${params.firstPort}"
                echo "three....${params.secondPort}"
                echo "current time is ${now}"
            

            }
            //  script {
            //                 sudo apt update
            // sudo apt install docker.io
            // sudo docker run -dit --name my-apache-app -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4
            // sudo docker ps
             // httpd --version
                
            //     }
            // run -u -dit --name my-apache-app -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4

        }
    }
}
