pipeline {
    agent {
        lable {
               label "built-in"
               customWorkspace "/data/projects"
}
}

    stages {
        stage("install-apache") {
            steps {
                sh "yum install httpd -y"
            }
        }
      stage("server-start") {
            steps {
                sh "service httpd start"
            }
        }  
        stage("deploy-index") {
            steps {
                sh "cp -r index.html /var/www/html"
                sh "chmod -R 777 /var/www/html"
            }
        }
    }
}
