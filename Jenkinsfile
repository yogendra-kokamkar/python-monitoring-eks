pipeline{
  agent any

  stages{
    stage('Code'){
        steps{
          git url: 'https://github.com/yogendra-kokamkar/python-monitoring-eks.git' branch: 'jenkins-cicd'
          sh 'ls -l'
     }
    
   }
 }
}
