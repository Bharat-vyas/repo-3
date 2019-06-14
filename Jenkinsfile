node {
      stage('Scm Checkout'){
      git credentialsId: '70879577-c865-415b-b4cb-0c6e86882477', url: 'https://www.github.com/Bharat-vyas/repo-3.git'
      }
      stage('view all Images'){
      //sh 'docker images'
      //sh 'ls -l'
      echo JOB_NAME;
      def scannerHome = env.JOB_NAME.replaceAll('%2'\'/','.');
     // def scannerHome3 = scannerHome.replace('%2','.');
            //def scannerHome3 = env.JOB_NAME.replaceAll("[% /]", ".");
           // def scannerHome2 = scannerHome3.replaceAll('.2','.');
            //echo scannerHome2;
      echo scannerHome;
              
     } 
      
      //stage('sed command')
      //{
      //s/h 'cat docker-compose.yml'
      //sh ("""sed -i '2 s/web_chat.*/web_chat:${env.BUILD_ID}/' docker-compose.yml""")
      //sh 'cat docker-compose.yml'
      //}

/*
      withCredentials([usernamePassword(credentialsId: '69_server', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')]) 
{
  def remote = [:]
  remote.name = 'VM'
  remote.host = '172.16.16.69'
  remote.user = "${USERNAME}"
  remote.password = "${PASSWORD}"
  remote.allowAnyHosts = true
  stage('Pull and Deploy Web Image') 
  {
    //have to use ssh pipeline setup plugin to use sscCommand or sshPut type of functionalities.
    sshCommand remote: remote, command: "ls /home; hostname"
    //sshPut remote: remote, from: '../testjenkins', into: '/home'
    //sshCommand remote: remote, command: "docker-compose -f $webPath/docker-compose.yml down; sleep 5; docker-compose -f $webPath/docker-compose.yml up -d ; docker ps"
  }
}
     */
      
 
     /* stage ('Build and Push')
      {
      withDockerRegistry(credentialsId: 'privatereg', url: 'https://dockerregistry.ecosmob.net:5000') {   
      def image1 = docker.build("dockerregistry.ecosmob.net:5000/testimage:${env.BUILD_ID}", "--file docker/Dockerfile .")   
             image1.push()
       }
       }*/
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
