pipeline {
    agent {
        docker {
          // image 'mcr.microsoft.com/powershell'
          image 'node:14.5.0-slim'
          args '-p 3000:3000'
        }
    }
    environment {
      HOME="."
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        // stage('Test') {
        //     steps {
        //         sh './jenkins/scripts/test.sh'
        //     }
        // }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                // input message: 'Finished using the web site? (Click "Proceed" to continue)'
                // sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
