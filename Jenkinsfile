node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-3.git'
      }
      stage('view all Images'){
      sh 'docker images'
      } 
      stage ('build')
      {
      withDockerRegistry(credentialsId: '996ea76f-df01-4824-9db3-0bc3a7c24c21') {     
      def image1 = docker.build("bharatvyas/drinksavvy-api:v1", "--file docker/Dockerfile .")
             
               
       }
      }
      stage ('push')
      {
      //docker.withServer('dockerregistry.ecosmob.net:5000')
            withDockerServer([uri: "tcp://dockerregistry.ecosmob.net:5000"]) {
            withDockerRegistry(credentialsId: 'privatereg', url: 'dockerregistry.ecosmob.net:5000') {
                  image1.push() 
      }
            
            
      }
      cleanWs cleanWhenNotBuilt: false, cleanWhenSuccess: false
      properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '2', numToKeepStr: '4'))])
      } 
