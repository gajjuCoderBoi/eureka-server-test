pipeline {
    agent {
        docker {
            image 'maven:3.6.2-jdk-8'
            args '--privileged -u="root" -v /tmp/.m2:/root/.m2 -v /usr/local/bin/docker:/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Deployment') {
            steps {
                sh 'cf push'
//                script {
//                    pushToCloudFoundry cloudSpace: 'development', credentialsId: 'pcf', organization: 'general-assembly', target: 'api.run.pivotal.io'
//                }
            }
        }
    }
}
