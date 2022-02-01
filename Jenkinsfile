pipeline {

  agent any

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "************** MUNIT Test cases not executed as Mulesoft is Container edition"
      }
    }

     stage('Development') {     
        
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy'
      }
    }
     }
   }