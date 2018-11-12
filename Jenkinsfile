pipeline {
    agent any

    stages {
        stage('aws') {
            steps {
                sudo su - oss -c 'cd /home/oss/.aws/src/puppet/modules/aws_demo && puppet apply create.pp'
            }
        }
        stage('primary') {
            steps {
                sudo su - oss -c 'sh /home/oss/primary.sh'
            }
        }

        stage('secondary') {
            steps {
                sudo su - oss -c 'sh /home/oss/secondary.sh'
            }
        }
	stage('primary') {
            steps {
                sudo su - oss -c 'sh /home/oss/mysql.sh'
            }
        }
    }
}
