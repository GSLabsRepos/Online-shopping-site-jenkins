node{

    // stage('SCM Checkout')
    // {
    //     git credentialsId: '4cc785e9-441d-4818-a248-2bfb2148004d', url: 'https://github.com/GSLabsRepos/Online-shopping-site-jenkins.git'
    // }
    
    stage('Run Docker Compose File')
    {
        sh 'pwd'
        sh 'docker-compose build .'
        sh 'docker-compose up -d'
    }
  stage('PUSH image to Docker Hub')
    {
      /* withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u upasanatestdocker -p ${DHPWD}"
        }
        sh 'docker push vardhanns/phpmysql_app'
        */
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
             sh 'docker login -u "rohitnaikade264" -p "Ro-Hitman.45" docker.io'
             //sh 'sudo docker push upasanatestdocker/mysql'
             //sh 'sudo docker push upasanatestdocker/job1_web1.0'
             sh 'docker push rohitnaikade264/onlineShop'
            // sh 'docker push upasanatestdocker/mysql'
          
    }
}
