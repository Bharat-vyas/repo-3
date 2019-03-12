node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-2.git'
      // Through Snippet Generator "Checkout: checkout form version controller"
      }
      stage('view all docker containers'){
      sh 'docker ps -a'
      }
      stage('Create Docker Image and run container out of it in local system'){
      //sh 'docker build -t bharatvyas/image1 .'
      docker.image('mysql:5').withRun('-e "MYSQL_ROOT_PASSWORD=my-secret-pw" -p 3306:3306') { c ->
        /* Wait until mysql service is up */
        sh 'while ! mysqladmin ping -h0.0.0.0 --silent; do sleep 1; done'
        /* Run some tests which require MySQL */
        sh 'make check'
    }

      // sh 'docker run -itd bharatvas/image1'      
      }
      stage('Push image to dockerhub'){
      withDockerRegistry(credentialsId: '996ea76f-df01-4824-9db3-0bc3a7c24c21') { // Through Snippet Generator "WithDockerRegistry"
      // Or we can use one more simple method --> Through Snippet Generator"WithCredentials : Bind credentials to variables" 
      // we can use it wherever we need to provide any kind of password or credentials either PASSWORD OR KEYS 
      // EXAMPLE -->select WithCredentials then click on add select either KEY or USERNAME_PASSWORD or just SECRET TEXT(as we just want to hide our password) whatever you want
      // it will bind those credentials to a variable and call the variable 
      //     withCredentials([string(credentialsId: 'cdeds', variable: 'dockerhub')]) {  } 
      //     sh 'docker login -u bharatvyas -p $(dockerhub)'   --> calling the variable that contain the password
      sh 'docker push bharatvyas/image1'
      }
      }

      
}
