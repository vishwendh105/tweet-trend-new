pipeline {
    agent {
     node  {
            label 'maven'
         }
    }
       

    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
   }
}
}
