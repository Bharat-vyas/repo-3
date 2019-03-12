node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-2.git'
      // Through Snippet Generator "Checkout: checkout form version controller"
      }
      stage('view all docker containers'){
      sh 'docker ps -a'
      }
      stage('Create Docker Image and run container out of it in local system'){
      sh 'docker build -t bharatvyas/image1 .'
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
      stage('Do the SSH into remote host'){
      // For SSH into remote host we can use Snippet Generator "SSHAgent: SSH Agent" but for that we have to install SSH Agent plugin
      // Then click on Add --> now we can add the credentials either password based or key based as we want or as we are provided with  
     // sshagent(['70879577-c865-415b-b4cb-0c6e86882477']) { //here we use username as root and password as ec.....t
     // sh 'ssh root@68.183.92.169'
     // sh 'docker pull bharatvyas/image1'
     // }
      sshPublisher(publishers: [sshPublisherDesc(configName: 'server1', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''docker pull bharatvyas/image1
      docker run -itd docker.io/bharatvyas/image1
      docker ps''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])      
            
            
      }
      
}
