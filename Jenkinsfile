pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'echo hello' 
            }
        }
        stage('Test'){
            steps {
                sh 'sleep 10'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo success'
            }
        }
    }
}