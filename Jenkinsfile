pipeline {
    agent any
    
    stages {

        stage('pull scm') {
            steps {
                git branch: 'main', url: 'https://github.com/SomeshGumachi/Amazon-Jenkins.git'
            }
        }
       
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
    }
    
post {
    success{
         echo 'Build success'
      }
    
    failure{
       echo 'Failure in the build'
    }
  }
}
