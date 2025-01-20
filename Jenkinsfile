pipeline{
    agent{
        label 'jenkins_agent'
    }

    tools {
        maven 'Maven_3.9.6'
    }

    stages{
        stage('SCM Checkout'){
            steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Jeffrin-Devops/Maven_First.git']])
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

 
