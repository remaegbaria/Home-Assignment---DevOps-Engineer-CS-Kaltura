pipeline {
    agent any
    parameters {
    string(name: 'Name', defaultValue: '', description: 'What is your name?')
    string(name: 'firstPort', defaultValue: '', description: 'What is the first port?')
    string(name: 'secondPort', defaultValue: '', description: 'What is the second port?')
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
                echo "Deploying....${params.Name}"
                echo "Deploying....${params.firstPort}"
                echo "Deploying....${params.secondPort}"
            }
        }
    }
}
