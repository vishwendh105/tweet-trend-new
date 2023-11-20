pipeline { 
    agent {
     node  {
            label 'maven'
         }
    }
       
environment{
    PATH = "/opt/apache-maven-3.9.2/bin:$PATH"
}
    stages {
        stage("build") {
            steps {
                sh 'mvn clean deploy'
            }
            stage('Sonarqube') {
    environment {
        scannerHome = tool 'My-SonarQube-scanner'
    }
    steps {
        withSonarQubeEnv('My-SonarQube-server') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}
        }
    
    }
    }

