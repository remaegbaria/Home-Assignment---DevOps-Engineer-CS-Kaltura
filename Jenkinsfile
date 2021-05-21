pipeline {
    agent any
    parameters {
    string(name: 'Name', defaultValue: '', description: 'What is your name?')
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
            }
        }
    }
}
