
pipeline {
    agent any

    environment {
        registry = 'remawail/home_assignment'
        registryCredential = 'docker-hub-connection'
        dockerImage = ''
    }

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
                    //swap the name value in the html file to the value of the parameter
                    sh "sed -i 's/{NAME}/${params.Name}/' index.html"
            }
        }

        stage('Deploy HTML page') {
            steps {
                //build httpd image with the Dockerfile
                sh "docker build -t ${registry} ."

                    withCredentials([usernamePassword(credentialsId: 'docker-hub-connection', usernameVariable: 'USERNAME',
                         passwordVariable: 'PASSWORD')]) {
                        sh "docker login -u $USERNAME -p $PASSWORD && docker push ${registry} "
                         }

                //run httpd image with the the two ports
                sh "docker run -dit --name my-running-app-1 -p ${params.firstPort}:80 -p ${params.secondPort}:80 ${registry}"
            }

            post {
                //in case of success : send a success message for the devops-engineer channel in slack
                success {
                        slackSend channel: '#devops-engineer', color: '#217a36', message: 'The process was built successfully...'}

                //in case of failure : send a failure message for the devops-engineer channel in slack
                failure {
                        slackSend channel: '#devops-engineer', color: '#ed3424', message: 'Failure in the build process...'}
            }
        }
    }
}
