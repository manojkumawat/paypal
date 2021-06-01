pipeline {
    agent any 
    stages {
        stage('Git SCM') { 
            steps {
               git credentialsId: 'manojkumawat', url: 'https://github.com/manojkumawat/Paypal.git'
            }
        }
        stage('Maven Build ') { 
            steps {
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('Tomcat Deploy') { 
            steps {
                deploy adapters: [tomcat9(credentialsId: 'Deployment', path: '', url: 'http://52.3.247.91:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
