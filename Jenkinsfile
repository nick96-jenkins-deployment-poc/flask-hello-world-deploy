pipeline {
    stages {
	stage('Deploy') {
	    script {
		def props = readJSON('properties.json')
		ansiblePlaybook(
		    playbook: 'deploy.yml',
		    credentialsId: 'jenkins-digitalocean-ssh-key',
		    colorized: true,
		    sudo: true,
		    user: 'root',
		    inventory: "hosts",
		    extraVars: "tag=${props['tag']}"
		)
	    }
	}
    }
}
