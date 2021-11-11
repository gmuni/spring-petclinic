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
     stage('build') {
        steps {
           sh script: 'mvn clean package'
        }
     }
     stage('post build') {
        steps {
           junit 'spring-petclinic/target/surefire-reports/*.xml'
           archiveArtifacts 'spring-petclinic/target*.jar'
        }
     }
  }
}
