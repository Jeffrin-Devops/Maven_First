pipeline{
    agent {
        label 'Ansible_agent'
    }
     tools {
        maven 'Maven 3.9'
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

         stage('deployment'){
            steps{
                sh '/home/ec2-user/tomcat/ansible-playbook app.yml -e "build=${BUILD_NUMBER}"'
            }
        }
    }
}

 
