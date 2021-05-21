def currentTime
pipeline {
    agent any
    parameters {
    string(name: 'Name', defaultValue: '', description: 'What is your name?')
    string(name: 'firstPort', defaultValue: '', description: 'What is the first port?')
    text(name: 'secondPort', defaultValue: '', description: 'What is the second port?')
  }

     agent {
        docker {
                image 'maven:3.8.1-adoptopenjdk-11'
                args '-v $HOME/.m2:/root/.m2'
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
             script {
                currentTime = java.time.LocalDate.now()
                }
                sh "echo ${currentTime}"
                echo "Deploying....${params.Name}"
                echo "two....${params.firstPort}"
                echo "three....${params.secondPort}"
            }
        }
    }
}
