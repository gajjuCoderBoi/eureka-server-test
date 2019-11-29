pipeline {
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Deployment'){
            steps{
                dir("users-api"){
                    sh 'cf push'
                }
            }
        }
    }
}
