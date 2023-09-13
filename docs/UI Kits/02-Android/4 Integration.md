## Before you begin

Before installing the **UIKit Beta**, you need to create a CometChat application on the CometChatPro Dashboard, which comprises everything required in a chat service including users, groups, calls & messages. You will need the `App ID` , `AuthKey`, `Region` of your CometChat application when initializing the SDK.

**i. Register on CometChat 🧑‍💻**

- you need to first register on **CometChat Dashboard**. [Click here to sign up](https://app.cometchat.com/login).

**ii. Get Your Application Keys 🔑**

- Create a **new app**
- Head over to the **QuickStart** or **API & Auth Keys section** and note the **App ID**, **Auth Key**, and **Region**.

> Each CometChat application can be integrated with a single client app. Within the same application, users can communicate with each other across all platforms, whether they are on mobile devices or on the web.

---

## Prerequisites

Before you begin, ensure you have met the following requirements:

- ✅ You have Android Studio installed in your machine.
- ✅ You have an Android Device or emulator with Android Version 6.0 or above.
- ✅ You have read up on [CometChat Key Concepts.](https://www.cometchat.com/docs/java-uikit-beta/key-concepts)

---

## Get Started

You can start building a modern messaging experience in your app by installing the new UI Kit.

### Add UI Kit as Dependency

This developer kit is an add-on feature to CometChatPro Android SDK so installing it will also install the core Chat SDK.

#### **Step 1:** **Add the repository URL**

Open the **project level**`build.gradle` file, Add the below repository url In the repositories block under the `allprojects` section .

```groovy
allprojects {
  repositories {
    		__url to fetch uikit
        maven{
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat_maven_"
        }
        __url to fetch chat and call sdk package
        maven {
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat-pro-android_maven_"
        }
  }
}
```



> In the latest version of Android Studio you need to add the Maven url to your `settings.gradle` file

```groovy
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        __url to fetch uikit
        maven{
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat_maven_"
        }
        __url to fetch chat and call sdk package
        maven {
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat-pro-android_maven_"
        }
    }
}
```



#### **Step 2: Add Manifest Placeholder**

Open the **app level** `build.gradle` file and add your package name as shown in the code

```groovy
android {
		defaultConfig {
			...

			manifestPlaceholders = [file_provider: "YOUR_PACKAGE_NAME"] 
			__add your application package.
		}
	}
```



#### **step 3: Add Dependency**

Open the **app level**`build.gradle` file and add the below dependency to fetch the chat UI kit into your project

```java
dependencies {
          implementation 'com.cometchat:chat-uikit-android:4.0.0-beta.2'
}
```



#### **step 4: Enable Jetifier**

Open the `gradle.properties` and check if the below stated line is present or not, if not then simply add it.

```groovy
android.enableJetifier=true
```



---

### 1. Initialize Client App

The `init()` method initializes the settings required for CometChat. Please make sure to call this method before calling any other methods from CometChat SDK.

```java
String appID = "APP_ID"; __ Replace with your App ID
String region = "REGION"; __ Replace with your App Region ("eu" or "us")
String authKey= "AUTH_KEY"; __ Replace with your App ID

UIKitSettings uiKitSettings = new UIKitSettings.UIKitSettingsBuilder()
.setRegion(region)
.setAppId(appID)
.setAuthKey(authKey)
.subscribePresenceForAllUsers().build();
        
CometChatUIKit.init(this, uiKitSettings, new CometChat.CallbackListener<String>() {
            @Override
            public void onSuccess(String successString) {
               
            }

            @Override
            public void onError(CometChatException e) {
                
            }
        });
```



> Make sure you replace the **appId** with your CometChat _appId_ and _region_ with your app region in the above code.

### 2. Create User

This method takes a `User` object  as input parameters and returns the created `User` object if the request is successful.

```java
User user = new User();
user.setUid("user1"); __ Replace with the UID for the user to be created
user.setName("Kevin"); __ Replace with the name of the user

CometChatUIKit.createUser(user, new CometChat.CallbackListener<User>() {
   @Override
   public void onSuccess(User user) {
   	      Log.d(TAG,"Create User Successful : "+ user.toString());
   	}
  @Override
  public void onError(CometChatException e) {
          Log.e(TAG,"Create User Failed : "+  e.getMessage());
  	}
  });
```



### 3. Login User

The `login()` method returns the User object containing all the information of the `logged-in user.`

```java
CometChatUIKit.login(uid, new CometChat.CallbackListener<User>() {
            @Override
            public void onSuccess(User user) {
               Log.d(TAG, "Login Successful : " + user.toString());
            }

            @Override
            public void onError(CometChatException e) {
                Log.e(TAG, "Login Failed : " + e.getMessage());
            }
        });
```



> - We have set up 5 users for testing having UIDs: superhero1, superhero2, superhero3, superhero4, and superhero5.

---

## Launch UI Components

CometChat's UIKit is a set of pre-built UI components that allows you to easily craft an in-app chat with all the essential messaging features.