pipeline{


    agent {
        any {
            image 'ubuntu'
            args '-u root:sudo -v $HOME/workspace/onlineShopping'
        }
    }

    stages{

          stage('SCM Checkout')
            {

                steps{
                    git branch: 'main', credentialsId: '3452a1d3-41e2-4577-86bb-4f2b097b6bdb', url: 'https://github.com/GSLabsRepos/Online-shopping-site-jenkins.git'

                }
            }
    
          stage('Run Docker Compose File')
           {

               steps{
                   sh 'pwd'
                   sh 'docker-compose build .'
                   sh 'docker-compose up -d'
               }
               
            }
          stage('PUSH image to Docker Hub')
            {
             

              steps{
                  sh 'docker login -u "rohitnaikade264" -p "Ro-Hitman.45" docker.io'

                  sh 'docker push rohitnaikade264/onlineShop'
              }
              
            
          
            }
    }
    
}
