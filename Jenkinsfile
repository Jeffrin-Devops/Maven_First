pipeline{
    agent any

    tools {
        maven 'Maven_3.9.6'
    }

    stages{
        stage('SCM Checkout'){
            steps{
                git branch: 'main', credentialsId: '96cccbac-8475-497a-b92a-fd551fac8eee', url: 'https://github.com/Jeffrin-Devops/Maven_First.git'
            }

        }

        stage('Maven-Build'){
            steps{
                sh 'mvn clean install'
            }
        }

     

        stage('Nexus Upload'){
            steps{
                sh 'mvn -s settings.xml clean deploy'
            }
        }

 
