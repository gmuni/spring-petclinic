pipeline {
    agent { label 'node1'}
    triggers {
        cron('H * * * 1-5')
    }
    stages {
        stage('scm') {
            steps {
                git 'https://github.com/gmuni/spring-petclinic.git'        
            }
        }
    }
}
