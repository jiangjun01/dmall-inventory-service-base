pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }
    
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

        stage('Test') {
            steps {
                sh 'ls -l gradlew'
            }
                
        }
        
        stage('Build') {
            steps{
                sh './gradlew build'
                sh 'ls -l build/libs'
                sh 'echo "building..."'
                sh 'echo "clean.dfrfgt."'
                sh 'dir'
             }
        }
        stage('Dock Push') {
            steps{
                sh '.genImages.sh'
             }
        }
    }
}
