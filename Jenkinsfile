pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "Compiling PES1UG22CS713.cpp"
                g++ PES1UG22CS713.cpp -o PES1UG22CS713
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running the compiled program"
                ./PES1UG22CS713
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment step (Modify as needed)"
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
