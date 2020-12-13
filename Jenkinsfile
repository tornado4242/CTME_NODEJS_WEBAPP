node {
    
	

    
    def newApp
    def registry = 'hub.docker.com/repository/docker/tornado4242/microservices-node-todo-frontend'
    def registryCredential = 'dockerhub'
	
	stage('Git') {
		git 'https://github.com/tornado4242/CTME_NODEJS_WEBAPP'
	}
	stage('Building image') {
        docker.withRegistry( 'https://' + registry, registryCredential ) {
		    def buildName = registry + ":$BUILD_NUMBER"
			newApp = docker.build buildName
			newApp.push()
        }
	}
	stage('Registring image') {
        docker.withRegistry( 'https://' + registry, registryCredential ) {
    		newApp.push 'latest2'
        }
	}
    	stage('Removing image') {
        sh "docker rmi $registry:$BUILD_NUMBER"
        sh "docker rmi $registry:latest"
    }
    
}
