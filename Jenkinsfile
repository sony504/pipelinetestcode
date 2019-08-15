pipeline {
    agent {
        label "linux"
    }
    tools {
        maven 'Maven3.3.9'
        jdk 'java8'
    }
    stages {
        stage ('Initialize') {
            steps {
              
                    export M2_HOME=/usr/local/apache-maven
                    export M2=$M2_HOME/bin
                    export PATH=$M2:$PATH
 
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'cd NumberGenerator & mvn install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
