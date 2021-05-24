//variable for the current date
// def now = new Date()
def MY_NAME 
pipeline {
    agent any

    //params
    parameters {
        //get the name
        string(name: 'Name', defaultValue: '', description: 'What is your name?')
        //get the first port
        string(name: 'firstPort', defaultValue: '80', description: 'What is the first port?')
        //get the second port
        text(name: 'secondPort', defaultValue: '443', description: 'What is the second port?')
    }

    stages {
        //pass name parameter to html file (index.html)
        stage('pass parameter') {
            steps {
                script {
                    MY_NAME = "<h2>${params.Name}</h2>"
                    // sh "MY_NAME='<h2>${params.Name}</h2>'"
                    echo "${MY_NAME} > index.html"
                    sh 'cat index.html'
                // env.Parameter = params.Name
                // echo "your name is ${env.Parameter}"
                // echo "your name is ${now}"
                }
            }
        }

        //pull httpd image from docker hub
        stage('pull image') {
            agent {
                docker { image 'httpd:2.4' }
            }
            steps {
                echo 'pull image....'
            }
        }
        stage('Deploy HTML page') {
            agent any
            steps {
                //build httpd image with the Dockerfile
                sh 'docker build -t my-apache2 .'
                //run httpd image with the first port
                sh "docker run -dit --name my-running-app-1 -p ${params.firstPort}:80 my-apache2"
                //run httpd image with the second port
                sh "docker run -dit --name my-running-app-2 -p ${params.secondPort}:80 my-apache2"
            }

            post {
                //in case of success : send a success message for the devops-engineer channel in slack
                success {
                    script {
                        slackSend channel: '#devops-engineer', color: '#217a36', message: 'The process was built successfully...'}
                }

                //in case of failure : send a failure message for the devops-engineer channel in slack
                failure {
                    script {
                        slackSend channel: '#devops-engineer', color: '#ed3424', message: 'Failure in the build process...'}
                }
            }
        }
    }
}
