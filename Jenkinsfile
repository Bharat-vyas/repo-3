node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-3.git'
      }
      stage('view all Images'){
      sh 'docker images'
      }
      
      withDockerRegistry(credentialsId: '996ea76f-df01-4824-9db3-0bc3a7c24c21') {
      //withDockerRegistry(credentialsId: 'privatereg', url: 'dockerregistry.ecosmob.net:5000') {
      //def image1 = docker.build("dockerregistry.ecosmob.net:5000/test-image:${env.BUILD_ID}", "./docker/")
            
      def image1 = docker.build("bharatvyas/drinksavvy-api:v1", "./docker/")
            
      //image1.run("-it", "bash")
      //def image1 = docker.build("test-image", "./dockerfiles/test")  If Dockerfile is in other directory
      // docker.build('myService -f ${pwd}/Dockerfile'
        
            
       //withDockerServer([uri: "tcp://dockerregistry.ecosmob.net:5000"]) {
        //withDockerRegistry([credentialsId: 'docker-registry-credentials', url: "https://<my-docker-registry>/"]) {
            // we give the image the same version as the .war package
            //def image = docker.build("<myDockerRegistry>/<myDockerProjectRepo>:${branchVersion}", "--build-arg PACKAGE_VERSION=${branchVersion} ./tmp-docker-build-context")
            //image.push()      
            
       
    
              image1.push()  
       }
         
      // app.push("${env.BUILD_NUMBER}")
      // app.push("latest")
            
      cleanWs cleanWhenNotBuilt: false, cleanWhenSuccess: false
      properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '2', numToKeepStr: '4'))])
      
      } //withregistry close       
 } //node close
