node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-2.git'
      // Through Snippet Generator "Checkout: checkout form version controller"
      }
      stage('view all docker containers'){
      sh 'docker ps -a'
      }
      
      withDockerRegistry(credentialsId: '996ea76f-df01-4824-9db3-0bc3a7c24c21') {
      def image1 = docker.build("bharatvyas/my-image:${env.BUILD_ID}")
      //def testImage = docker.build("test-image", "./dockerfiles/test")  If Dockerfile is in other directory
      //customImage.inside {
      //  sh 'ls'
      // }
      image1.push()      /* Push the container to the custom Registry (the registry whoom credential we have used in withDockerRegistry, can be either Dockerhub credentials or can be Private Registry credentials ) */
      
      } //withregistry close       

} //node close
