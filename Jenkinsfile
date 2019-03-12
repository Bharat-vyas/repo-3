node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-2.git'
      // Through Snippet Generator "Checkout: checkout form version controller"
      }
      stage('view all docker containers'){
      sh 'docker ps -a'
      }
      
      def customImage = docker.build("my-image")

    //customImage.inside {
      //  sh 'ls'
   // }
      
}
