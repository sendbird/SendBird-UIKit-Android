# [Sendbird](https://sendbird.com) UIKit for Android

![Platform](https://img.shields.io/badge/platform-ANDROID-orange.svg)
![Languages](https://img.shields.io/badge/language-JAVA-orange.svg)

## Table of contents

  1. [Introduction](#introduction)
  1. [Before getting started](#before-getting-started)
  1. [Getting started](#getting-started)
  1. [Implementation guide](#implementation-guide)
  1. [UIKit at a glance](#uikit-at-a-glance)  

<br />

## Introduction

**Sendbird UIKit** for Android is a development kit with an user interface that enables an easy and fast integration of standard chat features into new or existing client apps. From the overall theme to individual styles such as colors and fonts, components can be fully customized to create an in-app chat experience unique to your brand identity.

> **Note**: Currently, UIKit for Android now supports both group channels and open channels.

### Benefits

- Easy installation
- Fully-featured chat with a minimal amount of code
- Customizable components, events, and views
- Customizable user list to enable chat among specified users

![ThemeLight](https://static.sendbird.com/docs/uikit/android/theme-light_20200416.png)

### More about Sendbird UIKit for Android

Find out more about Sendbird UIKit for Android on [UIKit for Android doc](https://sendbird.com/docs/uikit/v1/android/getting-started/about-uikit). If you have any comments or questions regarding bugs and feature requests, visit [Sendbird community](https://community.sendbird.com/c/sendbird-chat-uikit/34). 

<br />

## Before getting started

This section shows the prerequisites you need to check to use Sendbird UIKit for Android.

### Requirements

The minimum requirements for UIKit for Android are:

- `Android + (API level as 16 or higher)`
- `Java 8`
- `Support androidx only`
- `Gradle 4.0.1 or higher`

<br />

## Getting started

This section gives you information you need to get started with Sendbird UIKit for Android. 

### Try the sample app

Our sample app has all the core features of Sendbird UIKit for Android. Download the app from our GitHub repository to get an idea of what you can build with the actual UIKit before building your own project.

- https://github.com/sendbird/Sendbird-Android/tree/master/uikit

### Create a project

Go to `Android Studio` and create a project for UIKit for Android in the **Project window** as follows:

1. In the **Welcome to Android Studio** window, click **Start a new Android Studio project**.
2. In the **Select a Project Template** window, select **Empty Activity**, and click **Next**.
3. Enter your project name in the **Name** field in the **Configure your project** window.
4. Select your language as either **Java** or **Kotlin** from the **Language** drop-down menu.
5. Enable **Use androidx.*artifacts**.
6. Select minimum API level as 16 or higher.
![Create a project](https://static.sendbird.com/docs/uikit/android/getting-started-01_20200416.png)

### Install using Gradle

UIKit for Android is installed using `Gradle`. Begin by opening the **root** `build.gradle` file and adding code blocks as shown below:

```gradle
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:4.0.1'
    }
}

allprojects {
    repositories {
        google()
        jcenter()
        maven { url "https://jitpack.io" }
        maven { url "https://repo.sendbird.com/public/maven" }
    }
}
```

> **Note**: Make sure the above code blocks aren't added to your module `bundle.gradle` file.

Then, open the `build.gradle` file at the application level. For `Java` and `Kotlin`, add code blocks and dependencies as below:

```gradle
apply plugin: 'com.android.application'

android {
    ...

    dataBinding {
        enabled = true
    }

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }

    ...
}

dependencies {
    ...
    implementation 'com.sendbird.sdk:uikit:LATEST_VERSION'
    ...
}
```

Before saving the `build.gradle` file, check if you've enabled the data binding. Then, click the **Sync** button to apply all the changes.

> **Note**: UIKit SDK versions `2.1.1` or lower can be downloaded from JCenter until February 1, 2022. SDK versions higher than `2.1.1` will be available on Sendbird's remote repository.

<br />

## Implementation guide

### Initialize the UIKit

Next, initialize a `SendBirdUIKit` instance by passing the `SendBirdUIKitAdapter` instance as an argument to a parameter in the `SendBirdUIkit.init()` method. Refer below for more information:

> **Note**: The `SendBirdUIkit.init()` must be called once in the `onCreate()` method of the [`Application`](https://developer.android.com/reference/android/app/Application) instance of your client app.

```java
package com.example.uikitapplication;

import android.app.Application;

import com.sendbird.uikit.SendBirdUIKit;
import com.sendbird.uikit.adapter.SendBirdUIKitAdapter;
import com.sendbird.uikit.interfaces.UserInfo;

public class BaseApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        
        SendBirdUIKit.init(new SendBirdUIKitAdapter() {
            @Override
            public String getAppId() {
                return "2D7B4CDB-932F-4082-9B09-A1153792DC8D";  // The ID of the Sendbird application which UIKit sample app uses.
            }
            
            @Override
            public String getAccessToken() {
                return "";
            }
            
            @Override
            public UserInfo getUserInfo() {
                return new UserInfo() {
                    @Override
                    public String getUserId() {
                        return USER_ID;
                    }
                    
                    @Override
                    public String getNickname() {
                        return USER_NICKNAME;
                    }
                    
                    @Override
                    public String getProfileUrl() {
                        return "";
                    }
                };
            }
        }, this);
    }
}
```

> **Note**: In the above, you should specify the `APP_ID` of your Sendbird application in place of the `getAppId()`'s return value.

Add the created `BaseApplication` to the `AndroidManifest.xml`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.sendbird.uikitapplication">
    
    <application
        android:name=".BaseApplication"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                ...
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
```

```xml
<resources>
    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
    </style>

</resources>
```

The Sendbird UIKit has successfully been initialized. The next sections will provide a more in-depth look into the details of each component as well as how they can be customized.

<br />

## UIKit at a glance

Methods provided by Sendbird UIKit for Android automatically process data using our chat SDK. Using [`Activities`](https://developer.android.com/guide/components/activities/intro-activities) and [`Fragments`](https://developer.android.com/guide/components/fragments), chat can easily be added to your Android client app using the components below.

### SendBirdUIKit instance

This is the most important class in the UIKit. These interfaces can be used to initialize information and call all `Activity` components.

|Method|Description|
|---|---|
|init()|Initializes a `SendBirdUIKit` instance.|
|setDefaultTheme()|Changes the theme to the default theme. |
|isDarkMode()|Determines whether the theme mode is `ThemeMode.Dark`|
|getAdapter()|Retrieves the current registered `SendBirdUIKit` adapter.|
|setCustomUserListQueryHandler()|Imports your custom user list. If this isn’t implemented, the list of all users in the Sendbird server are displayed.|
|connect() |Connects to Sendbird server and update your profile.|
|disconnect() |Disconnects from Sendbird server.|
|updateUserInfo()| Updates user information for profile display.|
|setCustomParamsHandler()| Sets the handler for common custom.|
|getCustomParamsHandler()| Returns the custom params handler.|
|setUseDefaultUserProfile()| Determines whether the user profile is used.|
|shouldUseDefaultUserProfile()| Returns the set value regarding the use of user profile.|

### SendBirdUIKitAdapter

Listed below are the methods of the `SendBirdUIKitAdapter` class:

|Method|Description|
|---|---|
|getAppId()|Retrieves the `APP_ID` of your Sendbird application.|
|getUserInfo()|Retrieves the information of the current user|
|getAccessToken()|Retrieves the access token of the current user, which is required to provide in the `SendBirdUIKit.init()` method. Using the Platform API, you can create a user along with their own access token, or issue an access token to an existing user. If you don’t want to use an access token, you must specify the return value of the `UserInfo.getUserID()` in the `SendBirdUIKitAdapter.getUserInfo()` instead. (Default: **USER_ID**)|

### UserInfo

Listed below are the methods of the `UserInfo` class:

|Method|Description|
|---|---|
|getUserId()|Retrieves the ID of the current user that has been registered to Sendbird server.|
|getNickName()|Retrieves the current user's nickname. If the nickname hasn’t been set, `USER ID` is used instead by default.|
|getProfileUrl() |Retrieves the URL of the current user's profile image.|

### Other components

The UIKit also provides the following components. All components can be called while fragments and activities are running on the Android platform.

|Component|Description|
|---|---|
|ChannelList|Shows all channels a user has joined. |
|Channel|Shows the current channel a user has joined. From this component, users can send or receive messages.|
|CreateChannel|Shows all the users of your client app so you can create a channel. Users can be selected from this component to begin chatting.|
|InviteChannel|Shows all the users of your client app from the current channel so you can invite other users to join.|
|ChannelSettings|Changes the channel information.|
|MemberList|Shows the list of members in the current channel.|
|PromoteOperator|Shows the list of members in the current channel whom you can promote as an operator.|
|BannedList|Shows the list of members who are banned from the current channel.|
|Moderation|Shows the list of moderation options for the current channel.|
|MutedMember|Shows the list of members who are muted in the current channel.|
|OperatorList|Shows the list of members who are appointed as an operator in the current channel.|
