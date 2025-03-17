pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "Creating a new .cpp file"
                echo '#include <iostream>\\nusing namespace std;\\nint main() { cout << "Hello, Jenkins!"; return 0; }' > PES1UG22CS713-1.cpp
                
                echo "Compiling the .cpp file"
                g++ PES1UG22CS713-1.cpp -o PES1UG22CS713-1
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running the compiled program"
                ./PES1UG22CS713-1
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Pushing to GitHub"
                git config --global user.email "your-email@example.com"
                git config --global user.name "your-username"
                git add PES1UG22CS713-1.cpp
                git commit -m "Added PES1UG22CS713-1.cpp"
                git push origin main
                '''
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
