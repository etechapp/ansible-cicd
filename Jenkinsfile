pipeline {
<<<<<<< HEAD
    agent {
      label {
        label 'host01'
      }
    }
=======
    agent host01
>>>>>>> 967ca53b741381eb0194a55a5e63a61c5e732ad6
    
    tools
    {
       maven "maven"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/etechapp/ansible-cicd.git'
             
          }
        }
         stage('Tools Init') {
            steps {
                script {
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
      
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
 
        stage('Ansible Deploy') {
             
            steps {
               sh "ansible-playbook etechnginx.yaml -i inventories/dev/hosts --user jenkins "     
            }
        }
    }
}
