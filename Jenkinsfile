pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage (no compilation needed for Python)'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
                    python3 -c "
from calculator import add, multiply, subtract, divide

print(add(2, 3)) == 5 
print(multiply(2, 3)) == 6
print(subtract(5, 2)) == 3
print(divide(10, 2)) == 5
"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage (dummy)'
            }
        }
    }
}
