node{
     
    stage('SCM Checkout'){
        git url: 'https://github.com/MithunTechnologiesDevOps/java-web-app-docker.git',branch: 'master'
    }
    
    stage(" Maven Clean Package"){
      sh " mvn clean package"
    } 
    
    
    stage('Build Docker Image'){
        sh 'docker build -t kalyan468/docker/java-web-app:latest .'
    }
    
    stage('Push Docker Image'){
        withCredentials([string(credentialsId: 'Docker_Hub_Pwd', variable: 'Docker_Hub_Pwd')]) {
          sh "docker login -u kalyan468 -p ${Docker_Hub_Pwd}"
        }
        sh 'docker push kalyan468/docker/java-web-app:latest'
     }
     
   
     
}
