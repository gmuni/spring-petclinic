pipeline {
    agent {label 'master'}
    triggers {
        cron('H * * * 1-5')
    }
    parameters {
        string(name: 'MAVENGOAL', defaultValue: 'clean compile', description: 'Enter your maven goal')
    }
    stages {
        stage('scm') {
            steps {
                git 'https://github.com/wakaleo/game-of-life.git'        
            }
        }
      stage('build') {
        steps {
           sh script: "mvn ${params.MAVENGOAL}"
        }
     }
    }
}
