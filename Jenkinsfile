pipeline {
    agent {
     node  {
            label 'maven'
         }
    }
environment {
    PATH = "/usr/share/maven/bin:$PATH"
}
    
    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
   }
}
}
