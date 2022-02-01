pipeline {

  agent any
  
  environment {

    ANYPOINT_CREDS = credentials('ANYPOINT_CREDENTIALS')
			}

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
     
       environment {

    CLIENT_ID = credentials('DEV_CLIENT_ID')
    CLIENT_SECRET= credentials('DEV_CLIENT_SECRET')
					}
        
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy -Dusername -Danypoint.username="%ANYPOINT_CREDS_USR%" -Danypoint.PASSWORD="%ANYPOINT_CREDS_PSW%" -Danypoint.platform.client_id="%CLIENT_ID%" -Danypoint.platform.client_secret="%CLIENT_SECRET%"'
      }
    }
     }
   }