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

        // stage('Unit Testing and Linting') {
        //   steps {
        //       sh 'npm test --watch=false'
        //   }
        // }
    
        // stage('SonarQube analysis') {
        //   steps {
        //     echo "SonarQube"
        //     script {
        //       // requires SonarQube Scanner 2.8+
        //       scannerHome = tool 'My SonarQube Scanner';
        //     }
        //     withSonarQubeEnv('SonarQube') {
        //       sh "${scannerHome}/bin/sonar-scanner"
        //     }
        //   }
        // }

        // stage('Android Build') {
        //     steps {
        //         sh 'ionic cordova build android' 
        //     }
        // }

        // stage('IOS Build') {
        //     steps {
        //       sh 'ionic cordova build ios -- --buildFlag="-UseModernBuildSystem=0" --release'
        //     }
        // }

        // stage('IOS Archive') {
        //     steps {
        //       sh 'xcodebuild -workspace ./platforms/ios/MyApp.xcworkspace -scheme MyApp -sdk iphoneos -configuration development archive -archivePath $PWD/platforms/ios/build/MyApp.xcarchive'
        //     }
        // }

        // stage('IOS IPA') {
        //     steps {
        //       sh 'xcodebuild -exportArchive -archivePath $PWD/platforms/ios/build/MyApp.xcarchive -exportOptionsPlist ./platforms/ios/exportOptions.plist -exportPath $PWD/platforms/ios/build'
        //     }
        // }

        stage('IOS'){
          steps{
            xcodeBuild appURL: '', assetPackManifestURL: '', buildDir: '', buildIpa: true, bundleID: '', bundleIDInfoPlistPath: '', cfBundleShortVersionStringValue: '', cfBundleVersionValue: '', compileBitcode: false, configuration: 'Debug', developmentTeamID: '9Q7ES27ZH2', developmentTeamName: '', displayImageURL: '', fullSizeImageURL: '', ipaExportMethod: 'development', ipaName: '${BASE_NAME} ${SHORT_VERSION} ${BUILD_DATE}', ipaOutputDirectory: '', keychainName: '', keychainPath: '', keychainPwd: '', logfileOutputDirectory: '', provisioningProfiles: [[provisioningProfileAppId: 'com.sampleJenkinsApp', provisioningProfileUUID: '8c0750c1-cdb6-417e-87ed-5f8adc4bc764']], sdk: '', signingMethod: 'manual', symRoot: '', target: '', thinning: '', uploadBitcode: false, xcodeProjectFile: '', xcodeProjectPath: '', xcodeSchema: 'MyApp', xcodeWorkspaceFile: '', xcodebuildArguments: ''
            //xcodeBuild appURL: '', assetPackManifestURL: '', buildDir: '', buildIpa: true, bundleID: 'com.sampleJenkinsApp', bundleIDInfoPlistPath: '', cfBundleShortVersionStringValue: '', cfBundleVersionValue: '', cleanBeforeBuild: false, cleanResultBundlePath: false, configuration: 'Development', developmentTeamID: '9Q7ES27ZH2', developmentTeamName: 'Ajay Joseph', displayImageURL: '', fullSizeImageURL: '', generateArchive: true, ipaExportMethod: 'development', ipaName: 'MyApp', ipaOutputDirectory: '', keychainName: 'keychain', keychainPath: '/Library/Keychains', keychainPwd: 'Tcs@jnj', logfileOutputDirectory: '', provisioningProfiles: [[provisioningProfileAppId: 'com.sampleJenkinsApp', provisioningProfileUUID: '8c0750c1-cdb6-417e-87ed-5f8adc4bc764']], resultBundlePath: '', sdk: '', signingMethod: 'manual', symRoot: '', target: '', thinning: '', unlockKeychain: true, xcodeProjectFile: '', xcodeProjectPath: '', xcodeSchema: 'MyApp', xcodeWorkspaceFile: '', xcodebuildArguments: ''
          }
        }

        //xcodeBuild appURL: '', assetPackManifestURL: '', buildDir: '', buildIpa: true, bundleID: 'com.sampleJenkinsApp', bundleIDInfoPlistPath: '', cfBundleShortVersionStringValue: '', cfBundleVersionValue: '', cleanBeforeBuild: false, cleanResultBundlePath: false, configuration: 'Development', developmentTeamID: '9Q7ES27ZH2', developmentTeamName: 'Ajay Joseph', displayImageURL: '', fullSizeImageURL: '', generateArchive: true, ipaExportMethod: 'development', ipaName: 'MyApp', ipaOutputDirectory: '$workspace/platforms/ios/build', keychainName: 'keychain', keychainPath: '/Library/Keychains', keychainPwd: 'Tcs@jnj', logfileOutputDirectory: '', provisioningProfiles: [[provisioningProfileAppId: 'com.sampleJenkinsApp', provisioningProfileUUID: '8c0750c1-cdb6-417e-87ed-5f8adc4bc764']], resultBundlePath: '', sdk: '', signingMethod: 'manual', symRoot: '', target: '', thinning: '', unlockKeychain: true, xcodeProjectFile: '', xcodeProjectPath: '$workspace/platforms/ios', xcodeSchema: '$workspace/platforms/ios/MyApp', xcodeWorkspaceFile: '$workspace/platforms/ios/MyApp.xcworkspace', xcodebuildArguments: ''

        // stage('Functional Testing using Appium'){
        //   steps{
        //     build 'appium'
        //   }
        // }

        stage('App Upload and Distribution using Testfairy'){
          steps{
            sh 'sh testfairy-upload.sh ./platforms/ios/build/MyApp.ipa'
            sh 'sh testfairy-upload.sh ./platforms/android/app/build/outputs/apk/debug/app-debug.apk'
          }
        }

        // stage('APK Sign for android') {
        //   steps {
        //     // sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
        //     echo "Android"
        //   }
        // }

        // stage('Publish Android') {
        //   steps {
        //       echo "Publish Android"
        //   }
        // }

        // stage('Publish iOS') {
        //   steps {   
        //     echo "Publish iOS"
        //   }
        // }
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

