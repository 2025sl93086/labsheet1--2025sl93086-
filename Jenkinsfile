pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/2025sl93086/labsheet1--2025sl93086-.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Build stage running..."'
            }
        }

        stage('Test') {
            steps {
                sh '''
                python3 - <<EOF
import calculator

assert calculator.add(2,3) == 5
assert calculator.sub(5,3) == 2
assert calculator.mul(2,3) == 6
assert calculator.div(6,3) == 2

print("All tests passed")
EOF
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploy stage running..."
                mkdir -p ~/deployment
                cp calculator.py ~/deployment/
                '''
            }
        }
    }
}
