pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/httpd-with-vol3"
		}
	}
	stages {
		stage ("23Q3-with-vol3") {
			steps {
				sh "docker volume create vol3"
				sh "cp /mnt/httpd-with-vol3/index.html /var/lib/docker/volumes/vol3/_data"
				sh "docker run -itdp 802:80 -v vol1:/usr/local/apache2/htdocs --name 23Q3 httpd"
				sh "docker exec 23Q3 chmod 777 /usr/local/apache2/htdocs/index.html"
			}
		}
	}
}
