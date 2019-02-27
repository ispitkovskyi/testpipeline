pipeline {
    agent any
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }
    stages {
        stage('Build') {
            steps {
                script{
                    def person = 'Jenkins'
                    echo 'Building..'
                    echo "I said, ${Greeting} Mr. ${person}"
                }
            }
        }
        stage('Parallel Run'){
            parallel{
                stage('Test') {
                    steps {
                        echo 'Testing..'
                    }
                }
                stage('Test on Linux') {
                    steps {
                        echo 'Deploying....'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
