pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/httpd-with-vol1"
		}
	}
	stages {
		stage ("23Q1-with-vol1") {
			steps {
				sh "docker volume create vol1"
				sh "cp /mnt/httpd-with-vol1/index.html /var/lib/docker/volumes/baba/_data"
				sh "docker run -itdp 80:80 -v vol1:/usr/local/apache2/htdocs --name 23Q1 httpd"
				sh "docker exec 23Q1 chmod 777 /usr/local/apache2/htdocs/index.html"
			}
		}
	}
}
