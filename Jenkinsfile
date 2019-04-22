pipeline {
    agent any

    stages {
	stage('Deploy') {
	    steps {
		script {
		    def props = readJSON(file: 'properties.json')

		    ansiblePlaybook(
		    	playbook: 'deploy.yml',
		    	credentialsId: 'jenkins-digitalocean-ssh-key',
		    	become: true,
		    	user: 'root',
		    	inventory: "hosts",
		    	extraVars: [
		    	    "tag": "${props['tag']}"
		    	]
		    )
		}
	    }
	}
    }
}
