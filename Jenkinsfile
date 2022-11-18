pipeline{
    agent any

    tools{
        gradle "Gradle-7"
    }

    stages{
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

        stage('Tests') {
          steps{
            sh 'gradle test'
          } 
        }     
    }
}