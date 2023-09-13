You can integrate voice and video calling SDK to add calling functionality to your CometChat-enabled application.

To integrate, follow the below steps:

### 1. Add the Call SDK dependency

Open the **app level Grad`le file -`**`build.gradle` and add the below dependency to fetch the Calls SDK into your project

```groovy
dependencies {
	implementation 'com.cometchat:pro-android-calls-sdk:3.0.0'
}
```



> Before Adding the Call SDK dependency to your project's dependencies please make sure that you have completed the [chat uikit integration](https://www.cometchat.com/docs/v3/android-v4-uikit/integration).

### 2.  Launching the component

The calls SDK integration will now enable the [Call Buttons](https://www.cometchat.com/docs/v3/android-v4-uikit/call-buttons) components in the menu of [Message Header](https://www.cometchat.com/docs/v3/android-v4-uikit/message-header). This will allow users to initiate voice or video calls to other chat participants. Additionally, all the components listed in the calls module are available for integration in your project.