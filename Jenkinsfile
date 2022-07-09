pipeline {
  //agent any
  agent {
  docker { 
            image 'sravangcpdocker/terraform:7'
            args '-u root:root'
        }
        }
  
  stages {
    stage('mvn package') {
      steps {
        sh '''
            git clone https://github.com/sravan-github/spring-boot-hello-world.git
            ls -l
            cd spring-boot-hello-world
            mvn package
            '''
         //ansiblePlaybook credentialsId: 'ansible-key1', disableHostKeyChecking: true, installation: 'ansible', inventory: 'inventory/mariadb.hosts', playbook: 'install-book.yml'
      }
    }
  }
  post {
        always {
        	cleanWs deleteDirs: true
        }
    }
}
