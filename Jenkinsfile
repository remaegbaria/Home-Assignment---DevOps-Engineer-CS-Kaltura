
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
                docker build -t my-apache2 .
                docker run -dit --name my-running-app -p 8080:80 my-apache2
            '''
                echo "Deploying....${params.Name}"
                echo "two....${params.firstPort}"
                echo "three....${params.secondPort}"
                echo "current time is ${now}"
                // script{
                // // def attachments = [
                // // [
                // //     text: 'build mood!',
                // //     // fallback: 'Hey, Vader seems to be mad at you.',
                // //     color: '#ff0000'
                // // ]
                // // ]

                // //  slackSend channel: '#devops-engineer', color: 'good', message: "build...."
                // // slackSend channel: '#devops-engineer', color: 'good', message: "build....", teamDomain: 'homeassignmen-fob5197.slack.com', tokenCredentialId: 'Nizs79B93Ku8txI0TqQlLC7l'
                // }

            }
                  post{
                success{
                script{
                     slackSend channel: '#devops-engineer', color: '#217a36', message: "The process was built successfully..."
                }
                }
               failure{
               script{
                     slackSend channel: '#devops-engineer', color: '#ed3424', message: "Failure in the build process..."
                    }
                    }
                }

        }

    }
}
