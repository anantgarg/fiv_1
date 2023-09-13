**Pluto UIKit for Android Java** is a UI Kit library of pre-built components that help developers to easily craft an in-app chat system with all the essential messaging features. It includes customized and independent components that can be used anywhere within app.

---

## Before you begin

Before installing **UIKit for Android** , you need to create a CometChat application on the CometChatPro Dashboard, which comprises everything required in a chat service including users, groups, calls & messages. You will need the `App ID` , `AuthKey`, `Region` of your CometChat application when initializing the SDK.

**i. Register on CometChat 🧑‍💻**

- you need to first register on **CometChat Dashboard**. [Click here to sign up](https://app.cometchat.com/signup).

**ii. Get Your Application Keys 🔑**

- Create a **new app**
- Head over to the **QuickStart** or **API & Auth Keys section** and note the **App ID**, **Auth Key**, and **Region**.

> Each CometChat application can be integrated with a single client app. Within the same application, users can communicate with each other across all platforms, whether they are on mobile devices or on the web.

---

## Prerequisites

Before you begin, ensure you have met the following requirements:

- ✅ You have Android Studio installed in your machine.
- ✅ You have an Android Device or emulator with Android Version 6.0 or above.
- ✅ You have read up on [CometChat Key Concepts.](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/key-concepts)

---

## Get Started

You can start building a modern messaging experience in your app by installing Pluto UIKit. There is two way to Add **Android Pluto Ui Kit** as  given below.

### Add UI Kit as Dependency

This developer kit is an add-on feature to CometChatPro Android SDK so installing it will also install the core Chat SDK.

#### **Step 1:** **Add the repository URL**

Open the **project level**`build.gradle` file, Add the below repository url In the repositories block under the `allprojects` section .

```groovy
allprojects {
  repositories {
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
        maven {
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat-pro-android_maven_"
        }
    }
}
```



#### **Step 2: Add Menifest Placeholder**

Open the **app level** `build.gradle` file and add the below code.

```groovy
android {
		defaultConfig {
			...

			manifestPlaceholders = [file_provider: "YOUR_PACKAGE_NAME"] 
			__add your application package.
		}
	}
```



#### **step 3 : Enable Data binding**

Open the **app level** `build.gradle` file and add the below code.

```groovy
android {
    dataBinding {
        enabled = true
    }
}
```



#### **step 4: Enable Jetifier**

Open the `gradle.properties` and check if the below stated line is present or not, if not then simply add it.

```groovy
android.enableJetifier=true
```



#### **step 5: Add Dependency**

Open the **app level**`build.gradle` file and add the below dependency.

```groovy
dependencies {
      implementation 'com.cometchat:pro-android-java-chat-ui-kit:3.0.9-pluto.beta1'
}
```



---

### Add Ui Kit as Module

To Add UiKit as Module into your app, please refer to the steps below.

#### **Step 1:** **Add the repository URL**

Open the **project level**`build.gradle` file, Add the below repository url In the repositories block under the `allprojects` section .

```groovy
allprojects {
  repositories {
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
        maven {
            url "https:__dl.cloudsmith.io_public_cometchat_cometchat-pro-android_maven_"
        }
    }
}
```



#### **Step 2:** **Add the CometChat Dependencies**

Open the **app level**`build.gradle` file and add the below dependency.

```groovy
dependencies {  
		implementation 'com.cometchat:pro-android-chat-sdk:3.0.9'
    implementation 'com.cometchat:pro-android-calls-sdk:2.2.0'
}
```



#### **Step 3: Download pluto UiKit Module**

- Clone the UI Kit Library from the [android-chat-ui-kit repository](https://github.com/cometchat-pro/android-java-chat-ui-kit/tree/pluto), or

<p style="margin-left:30px;"><a class="button" style="background:#6929CA;color:#fff;" href="https://github.com/cometchat-pro/android-java-chat-ui-kit/archive/pluto.zip"><i class="fa fa-download"></i> Download UI Kit Library</a></p>

#### **Step 4: Import Pluto UIkit**

To import UIKit module in your app please refer to the steps below :

- Go to **File &gt;&gt; New &gt;&gt; Import Module...** Select the source directory of the Module you want to import and click Finish. 

![](https://uploads.developerhub.io/prod/x9W8/ubnlln02iq0y3hxryv8aruhxaluyfqpda81r2v6zz26ghamr9rnbwfi50u5iim7n.png)

- Now you will see the CometChatWorkspace module is added to your project.

![](https://uploads.developerhub.io/prod/x9W8/beqvkv7vl3kx0blkydeh8xtyvmnnz82z0k3d2153jgo1gmd3x6b1d9a9sb3irghp.png)

- Now to integrate the **Pluto** **uikit** in project developer have to copy and paste the following code in **app level** `build.gradle`.

```groovy
dependencies {
		implementation project(path: ':CometChatWorkspace')
}
```



#### **Step 5: Add Menifest Placeholder**

Open the **app level** `build.gradle` file and add the below code.

```groovy
android {
		defaultConfig {
			...

			manifestPlaceholders = [file_provider: "YOUR_PACKAGE_NAME"] 
			__add your application package.
		}
	}
```



#### **step 6 : Enable Data binding**

Open the **app level** `build.gradle` file and add the below code.

```groovy
android {
    dataBinding {
        enabled = true
    }
}
```



#### **step 7: Enable Jetifier**

Open the `gradle.properties` and check if the below stated line is present or not, if not then simply add it.

```groovy
android.enableJetifier=true
```



---

## Initialize CometChat

### 1. Initialize Client App

The `init()` method initializes the settings required for CometChat. We suggest calling the `init()` method on app startup, i.e very first Activity of the Application.

```java
String appID = "APP_ID"; __ Replace with your App ID
String region = "REGION"; __ Replace with your App Region ("eu" or "us")

AppSettings appSettings = new AppSettings.AppSettingsBuilder()
  .subscribePresenceForAllUsers()
  .setRegion(region)
  .build();

 CometChat.init(this, appID, appSettings,
                new CometChat.CallbackListener<String>() {
                    @Override
                    public void onSuccess(String s) {
                       
                        CometChat.setSource("ui-kit", "android", "java");
                    }

                    @Override
                    public void onError(CometChatException e) {
                        Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_SHORT).show();
                    }
                });
```



> Make sure you replace the **appId** with your CometChat _appId_ and _region_ with your app region in the above code.

### 2. Create User

This method takes a `User` object and the `Auth Key` as input parameters and returns the created `User` object if the request is successful.

```java
String authKey = "AUTH_KEY"; __ Replace with your App Auth Key
User user = new User();
user.setUid("user1"); __ Replace with the UID for the user to be created
user.setName("Kevin"); __ Replace with the name of the user

CometChat.createUser(user, authKey, new CometChat.CallbackListener<User>() {
  @Override
    public void onSuccess(User user) {
    Log.d("createUser", user.toString());
  }

  @Override
    public void onError(CometChatException e) {
    Log.e("createUser", e.getMessage());
  }
});
```



### 3. Login User

The `login()` method returns the User object containing all the information of the `logged-in user.`

```java
String UID = "user1"; __ Replace with the UID of the user to login
String authKey = "AUTH_KEY"; __ Replace with your App Auth Key

 if (CometChat.getLoggedInUser() == null) {
     CometChat.login(UID, authKey, new CometChat.CallbackListener<User>() {

      @Override
      public void onSuccess(User user) {
        Log.d(TAG, "Login Successful : " + user.toString());
  }

   @Override
    public void onError(CometChatException e) {
        Log.d(TAG, "Login failed with exception: " + e.getMessage());
   }
 });
 } else {
   __ User already logged in
 }
```



> - Make sure you replace the authKey with your CometChat Auth Key in the above code.> - We have set up 5 users for testing having UIDs: SUPERHERO1, SUPERHERO2, SUPERHERO3, SUPERHERO4, and SUPERHERO5.

---

## Launch UI Components

The UIKit is a set of pre-built UI components that allows you to easily build beautiful in-app chat with all the essential messaging features.

| Components | Description | Link | 
| ---- | ---- | ---- | 
| **`UI Components`** | CometChat's UIKit is a set of pre-built UI components that allows you to easily craft an in-app chat with all the essential messaging features. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/ui-components) | 
