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

        stage('Deploy') {
            when {
                expression { 
                    return env.GIT_BRANCH?.contains('release') 
                }
            }
            steps {
                echo 'Release branch detected. Deploying...'
            }
        }
    }
    
post {
    success{
         echo 'Build and deploy is success'
      }
    
    failure{
       echo 'Failure in the build or deploy'
    }
  }
}
