pipeline {
    agent any
    
    stages {
        stage('repo clean up'){
            steps {
                step([$class: 'WsCleanup'])
            }
        }

        stage('Checkout') {
            steps {
                git poll: true, url: 'https://github.com/jiangjun01/dmall-inventory-service-base.git', branch: 'master'
            }
                
        }

        stage('Build') {
            steps{
                sh 'echo "building..."'
                sh 'echo "clean..."'
                sh 'echo "jjj"'
            }
        }
    }
}
