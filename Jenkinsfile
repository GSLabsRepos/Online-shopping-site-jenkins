pipeline{


    agent {
        docker {
            image 'ubuntu'
            args '-u root:sudo -v $HOME/workspace/onlineShopping'
        }
    }

    stages{

          stage('SCM Checkout')
            {
                git branch: 'main', credentialsId: '3452a1d3-41e2-4577-86bb-4f2b097b6bdb', url: 'https://github.com/GSLabsRepos/Online-shopping-site-jenkins.git'
            }
    
          stage('Run Docker Compose File')
           {
               sh 'pwd'
               sh 'docker-compose build .'
               sh 'docker-compose up -d'
            }
          stage('PUSH image to Docker Hub')
            {
             
              sh 'sudo docker login -u "rohitnaikade264" -p "Ro-Hitman.45" docker.io'
             //sh 'sudo docker push upasanatestdocker/mysql'
             //sh 'sudo docker push upasanatestdocker/job1_web1.0'
             sh 'sudo docker push rohitnaikade264/onlineShop'
            // sh 'docker push upasanatestdocker/mysql'
          
            }
    }
    
}
