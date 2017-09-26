# VWO ANDROID SNAPSHOT REPOSITORY
Snapshot repository for Android VWO SDK.

## Requirements

* Android 4.0 (API 14) or later

## Credentials

This SDK requires an app key. You can sign up for an account at [VWO](https://vwo.com).
Once there, you can add a new Android App, and use the generated app key in the app.

## Setting up VWO account
* Sign Up for VWO account at https://vwo.com
* Create a new android app from create menu
* Use the app generated app key, while integrating SDK into android app.
* Create and run campaigns.


## How to import in gradle:
In your top level build.gradle file add the following code under repositories.

    buildscript {
        ...
        repositories {
            ...
        }
    }

    allprojects {
        repositories {
            ...
            maven {
                url 'https://raw.githubusercontent.com/wingify/vwo-android-snapshot/master/'
            }
            ...
        }
    }

Add dependencies to app/build.gradle file

    dependencies {
        ...
        compile 'com.vwo:mobile:2.0.0-SNAPSHOT'
        // Add this library to debug compile mode only.
        debugCompile ('io.socket:socket.io-client:1.0.0') {
            // excluding org.json which is provided by Android
            exclude group: 'org.json', module: 'json'
        }
        compile 'io.sentry:sentry-android:1.4.0'

        // Skip this if you are already including support library in your app.
        compile 'com.android.support:support-core-utils:26.0.2'
        ...
    }