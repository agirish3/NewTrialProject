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
              sh 'npm test --watch=false'
            // echo "Unit Test Case Execution 1/2 in progress..."
            // echo "Completed..."
            // echo "Unit Test Case Execution 2/2 in progress..."
            // echo "Completed..."
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

        stage('Testing'){
          steps{
            build 'appium'
          }
        }

        // stage('IOS Build') {
        //     steps {
        //       sh 'ionic cordova build ios -- --buildFlag="-UseModernBuildSystem=0"'
        //       //sh 'ionic cordova run ios -- --buildFlag="-UseModernBuildSystem=0" --release'
        //     }
        // }

        stage('APK Sign for android') {
          steps {
            // sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
            echo "Android"
          }
        }

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

