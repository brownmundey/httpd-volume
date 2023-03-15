pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/httpd-with-vol2"
		}
	}
	stages {
		stage ("23Q2-with-vol2") {
			steps {
				sh "docker volume create vol2"
				sh "cp /mnt/httpd-with-vol2/index.html /var/lib/docker/volumes/vol2/_data"
				sh "docker run -itdp 801:80 -v vol1:/usr/local/apache2/htdocs --name 23Q2 httpd"
				sh "docker exec 23Q2 chmod 777 /usr/local/apache2/htdocs/index.html"
			}
		}
	}
}
