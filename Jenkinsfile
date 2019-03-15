node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-3.git'
      }
      stage('view all Images'){
      sh 'docker images'
      } 
      stage ('Build and Push')
      {
      withDockerRegistry(credentialsId: 'privatereg', url: 'https://dockerregistry.ecosmob.net:5000') {   
      def image1 = docker.build("dockerregistry.ecosmob.net:5000/testimage:v1", "--file docker/Dockerfile .")   
             image1.push()
       }
      }
}
      
     // stage ('push')
      //{
      //withDockerServer([uri: "dockerregistry.ecosmob.net:5000"]) {
      //docker.withServer('tcp://dockerregistry.ecosmob.net:5000'){
   //   withDockerRegistry(credentialsId: 'privatereg', url: 'https://dockerregistry.ecosmob.net:5000') {
     //       image1.push()
      //}
      //}
      //}
             
      //cleanWs cleanWhenNotBuilt: false, cleanWhenSuccess: false
      //properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '2', numToKeepStr: '4'))])
       
