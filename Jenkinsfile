pipeline{
  agent any

  stages{
    stage('Code'){
        steps{
          git url: 'https://github.com/yogendra-kokamkar/python-monitoring-eks.git', branch: 'jenkins-cicd'
        }
   }
    stage('Build'){
        steps{
          sh 'docker build -t yogendrakokamkar/monitor .'
        }
   }

    stage('Push'){
            steps{
                withCredentials([usernamePassword(credentialsId: 'docker', passwordVariable: 'DockerPassword', usernameVariable: 'DockerUser')]) {
        	       sh "docker login -u ${env.DockerUser} -p ${env.DockerPassword}"
                 sh 'docker push yogendrakokamkar/monitor'
                }
            }
        }
  }
}
