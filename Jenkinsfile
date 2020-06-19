node{
    
    def remote = [:]
    remote.name = 'DEPLOYMENT-SERVER'
    remote.host = '192.168.50.10'
    remote.user = 'root'
    remote.password = 'emran123'
    remote.allowAnyHosts = true
     
    stage('Cleanup Workspace'){
        cleanWs()
    } 
     
    stage('SCM Checkout'){
        git credentialsId: 'gitcred', url: 'https://github.com/Emran111/bs-test'
    }

    stage('Build Containers'){
        sh label: 'Build docker containers', script: 'docker-compose build'
   }   
   
    stage('Deploy Containers'){
        sh label: 'Deploy docker containers', script: 'docker-compose up -d'
   } 

}