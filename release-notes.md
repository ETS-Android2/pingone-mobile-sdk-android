# Release Notes

## v1.7.0 - April 25th, 2022
Features:

- Updated SDK to version 1.7.0
- Added support for authentication using QR Code scanning or manual typing of an authentication code
- Added Certificate Transparency mechanism to protect against mis-issued certificates
- The JWT signature validation updated to use more strong EC algorithm. 


Compatibility:
- Minimal Android version is updated to 26 (Android 8)
- Dependencies updated to their latest versions:
    * In the 'build.gradle' file at the **project** level:
        * 'com.android.tools.build:gradle:**7.1.1**'
        * 'com.google.gms:google-services:**4.3.10**'
        * 'androidx.navigation:navigation-safe-args-gradle-plugin:**2.3.5**'
    * In the 'build.gradle' file at the **app** level:
        * 'org.bitbucket.b_c:jose4j:**0.7.9**'
        * 'com.google.android.gms:play-services-safetynet:**18.0.1**'
        * 'com.google.code.gson:gson:**2.8.9**'  
- Dependencies added:    
    * In the 'build.gradle' file at the **app** level:
        * 'com.appmattus.certificatetransparency:certificatetransparency-android:1.0.0'
    

## v1.6.0 - August 1st, 2021
Features:

- Updated SDK to version 1.6.0.
- Added support for device integrity validation for threat protection.


Compatibility:
 - Dependencies updated to their latest versions:
      * In the 'build.gradle' file at the **project** level:
        * 'com.android.tools.build:gradle:**4.2.1**'
        * 'com.google.gms:google-services:**4.3.8**'
        * 'androidx.navigation:navigation-safe-args-gradle-plugin:**2.3.5**'
     * In the 'build.gradle' file at the **app** level:
        * Migrated to FireBase BOM:
          * implementation platform('com.google.firebase:firebase-bom:26.3.0')
          * implementation 'com.google.firebase:firebase-core'
          * implementation 'com.google.firebase:firebase-messaging'
         * 'androidx.appcompat:appcompat:**1.3.0**'
           

## v1.5.0 - April 6th, 2021
Features:
- Updated SDK to version 1.4.0.
- Added support for one time passcode and disable SDK push notifications.

Compatibility notes:
- Deprecated current pairing method and added support to new one with returned object of PairingInfo.
- Deprecated current processRemoteNotification method and added support to new one with Context as a parameter.

Dependencies updated:
- com.android.tools.build:gradle:4.0.1
- com.google.gms:google-services:4.3.4

## v.1.4.1 - Feb 3rd, 2021
Bug fixes:
 - Added a missing dependency in the project-level `build.gradle` file.
 - Fixed a dead link from README
 
 
## v1.4.0 - Jan 5th, 2021
Features:

- Added support for Mobile Authentication Framework for Android Developers. 
See the files in the `PingAuthenticationUI` and `PingAuthenticationCore` folders.


## v1.3.0 - June 18th, 2020
Features:

- Push notification data is now JWT-signed and verified
- Added `clientContext` to the push notification object. `clientContext` contains extra parameters that are passed to the client.
- Added support for background push notification (extra verification) during device authorization

Dependencies updated:

  * 'com.android.tools.build:gradle:3.5.3'
  * 'com.google.gms:google-services:4.3.3'
  * 'com.google.firebase:firebase-core:17.4.2'
  * 'com.google.firebase:firebase-messaging:20.2.0'


Compatibility notes:

- Deprecated method: `PingOne.processRemoteNotification(RemoteMessage remoteMessage, PingOne.PingOneNotificationCallback callback)`
  Instead please use:
 `PingOne.processRemoteNotification(Context context, RemoteMessage remoteMessage, PingOne.PingOneNotificationCallback callback)`


## v1.2.0 - March 31st, 2020
Features:

- Support for sending logs (both by app and admin)
- Ability to track authentication expiration time in the app

## v1.1.0 - December 9th, 2019
Features:

- Support for automatic pairing via OpenID Connect authentication.
- The `pair()` function now returns error code 10007 `PAIRING_KEY_DATA_CENTER_MISMATCH` when trying to pair a user in a different geographical datacenter than the users already paired on the device.

Compatibility notes:

- Deprecated functions: `NotificationObject.approve(Context context, PingOne.PingOneSDKCallback callback)`
- Sample app now using AppAuth 0.7.1

## v1.0.2 - October 30th, 2019
Features:
- Support for APAC datacenter.

## v1.0.1 - October 10th, 2019
Features:
- added a notification pop up in the sample app.

Bug fixes:
- Handle test push without producing an error.

Compatibility notes:
- replace NimbusDS with Jose4J.


## v1.0 - August 1st, 2019
Features:
- Provide MFA capability (using push notifications) for Android native apps.

