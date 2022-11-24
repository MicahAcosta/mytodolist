pipeline{
    agent any

    tools{
        gradle 'Gradle-6'
    }

    stages
    {
        stage('clone repository') {
          steps{
            git 'https://github.com/MicahAcosta/mytodolist.git'
          } 
        }

        stage('Build the project') {
          steps{
            sh 'gradle build'
          } 
        }    

       /* stage('Test') {
          steps{
            sh 'gradle test'
          } 

        } */


       stage('Deploy to Heroku') {
         steps {
           withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
           sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/aqueous-inlet-48593.git master'
             }
            }
        }    
    }
}