pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/car.txt'
                sh 'echo "nati" > build/car.txt'
                sh 'echo "malkiel" >> build/car.txt'
                sh 'echo "devops" >> build/car.txt'
            }
        }
        stage('Test'){
            steps {
                sh 'test -f build/car.txt'
                sh 'grep "nati" build/car.txt'
                sh 'grep "malkiel" build/car.txt'
                sh 'grep "devops" build/car.txt'
            }
        }
        stage('Publish'){
            steps{
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
