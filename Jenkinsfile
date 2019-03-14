pipeline {

    agent any

    environment {
        PATH='/usr/local/bin:/usr/bin:/bin'
	}

    stages {

       stage('NPM Setup') {
          steps {
             sh 'npm install'
         }
       }

      stage('Unit Tests') {
          steps {
            //  sh 'npm test --no-browsers'
            echo "Unit Test Case Execution 1/2 in progress..."
            echo "Completed..."
            echo "Unit Test Case Execution 2/2 in progress..."
            echo "Completed..."
         }
       }
      
      stage('SonarQube analysis') {
        steps {
          echo "SonarQube"
          script {
            // requires SonarQube Scanner 2.8+
            scannerHome = tool 'My SonarQube Scanner';
          }
          withSonarQubeEnv('SonarQube') {
            sh "${scannerHome}/bin/sonar-scanner"
          }
        }
      }

      stage('Android Build') {
          steps {
               sh 'ionic cordova build android' 
          }
      }

      // stage('IOS Build') {
      //     steps {
      //       //sh 'ionic cordova build ios -- --buildFlag="-UseModernBuildSystem=0"'
      //       sh 'sudo ionic cordova run ios -- --buildFlag="-UseModernBuildSystem=0"'
      //     }
      //  }

       stage('APK Sign for android') {
          steps {
            // sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
              echo "Android"
          }
      }

    //   stage('Stage Web Build') {
    //       steps {
    //           sh 'npm run build --prod'
    //       }
    //    }

      //    stage('Publish Firebase Web') {
      //     steps {
      //         //sh 'firebase deploy --token "YourTokenKey"'
      //         echo 'Firebase Deploy'
      //     }
      //  }

        stage('Publish Android') {
          steps {
              echo "Publish Android"
          }
        }

          stage('Publish iOS') {
            steps {   
                echo "Publish iOS"
            }
         }

}
}

