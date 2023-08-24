This section will guide you to start the call/conference directly with the session id of your choice. The session id is the most important parameter as all the users joining the same session id will be connected to the same call/conference.

## Implementation

The most important class that will be used in the implementation is the `CallSettings` class. This class allows you to set the various parameters for the call/conference. In order to set the various parameters of the `CallSettings` class, you need to use the `CallSettingsBuilder` class. Below are the various options available with the `CallSettings` class.

CallSettingsBuilder class takes the 2 mandatory parameters as a part of the constructor:

1. Context of the application
2. An object of the RelativeLayout. The calling UI will be loaded in this relative layout provided.

The other mandatory parameter is the sessionId for the call/conference. You can use the setSessionId() method of the `CallSettingsBuilder` to set the session Id of the call.

A basic example of how to start a direct call:

```java
String sessionID = "SESSION_ID";
RelativeLayout callView;
Activity activity;
boolean audioOnly;

CallSettings callSettings = new CallSettings.CallSettingsBuilder(activity,callView)
  .setSessionId(sessionId)
  .setIsAudioOnly(audioOnly)
  .build();

CometChat.startCall(callSettings, new CometChat.OngoingCallListener() {
  @Override
  public void onUserJoined(User user) {
    Log.d(TAG, "onUserJoined: Name "+user.getName());
  }

  @Override
  public void onUserLeft(User user) {
    Log.d(TAG, "onUserLeft: "+user.getName());
  }

  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "onError: "+e.getMessage());
  }

  @Override
  public void onCallEnded(Call call) {
    Log.d(TAG, "onCallEnded: "+ call.toString());
  }

  @Override
  public void onUserListUpdated(List<User> list) {
    Log.d(TAG, "onUserListUpdated: "+ list.toString());
  }

  @Override
  public void onAudioModesUpdated(List<AudioMode> list) {
    Log.d(TAG, "onAudioModesUpdated: "+ list.toString());
  }

});
```

```kotlin
val sessionID = "SESSION_ID"
var callView: RelativeLayout
var activity: Activity
var audioOnly: Boolean

val callSettings: CallSettings = CallSettingsBuilder(activity, callView)
  .setSessionId(sessionId)
  .setIsAudioOnly(audioOnly)
  .build()

CometChat.startCall(callSettings, object : OngoingCallListener {
  override fun onUserJoined(user: User) {
    Log.d(TAG, "onUserJoined: Name " + user.name)
  }

  override fun onUserLeft(user: User) {
    Log.d(TAG, "onUserLeft: " + user.name)
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "onError: " + e.message)
  }

  override fun onCallEnded(call: Call) {
    Log.d(TAG, "onCallEnded: " + call.toString())
  }

  override fun onUserListUpdated(list: List<User>) {
    Log.d(TAG, "onUserListUpdated: $list")
  }

  override fun onAudioModesUpdated(list: List<AudioMode?>) {
    Log.d(TAG, "onAudioModesUpdated: $list")
  }
})
```



The `setAudioOnlyCall()` method allows you to set if the call is supposed to be an audio call or an audio-video call. If set to true, the call will be an audio-only call else when set to false the call will be an audio-video call. The default will is false, so if not set, the call will be an audio-video call.

| Parameter | Description | 
| ---- | ---- | 
| `activity` | The activity that you want to show the calling view in. | 
| `sessionID` | The unique random session ID. | 
| `RelativeLayout` | An object of the relativeLayout class in which CometChat can load the calling views | 


The `OngoingCallListener` listener provides you with the below callback methods:

| Callback Method | Description | 
| ---- | ---- | 
| `onUserJoined(User user)` | This method is called when any other user joins the call. The user details can be obtained from the `User` object provided. | 
| `onUserLeft(User user)` | This method is called when a user leaves the call. The details of the user can be obtained from the provided `User` object. | 
| `onError()` | This method is called when there is some error in establishing the call. | 
| `onCallEnded()` | This method is called when the call is successfully ended. The call details can be obtained from the `Call` object provided. | 
| `onUserListUpdated(List<User> users)` | This method is triggered every time a participant joins or leaves the call providing the list of users active in the call | 
| `onAudioModesUpdated(List<AudioMode> audioModes)` | This callback is triggered if any new audio output source is available or becomes unavailable. | 
| `onUserMuted(User userMuted, User userMutedBy)` | This method is triggered when a user is muted in the ongoing call. | 
| `onCallSwitchedToVideo(String sessionId, User callSwitchInitiatedBy, User callSwitchAcceptedBy)` ` | This callback is triggered when an audio call is converted into a video call. | 


## Settings

The `CallSettings` class is the most important class when it comes to the implementation of the Calling feature. This is the class that allows you to customize the overall calling experience. The properties for the call/conference can be set using the `CallSettingsBuilder` class. This will eventually give you and object of the `CallSettings` class which you can pass to the `startCall()` method to start the call.

The **mandatory** parameters that are required to be present for any call/conference to work are:

1. Context - context of the activity/application
2. RelativeLayout - A RelativeLayout object in which the calling UI is loaded.
3. sessionId - The unique session Id for the call/conference session.

The options available for customization of calls are:

| Setting | Description | 
| ---- | ---- | 
| `enableDefaultLayout(boolean b)` | If set to `true` enables the default layout for handling the call operations. \n\n\n\nIf set to `false` it hides the button layout and just displays the Call View\n\n\n\n**Default value = true** | 
| `showAudioModeButton(boolean b)` | If set to `true` it displays the AudioModeButton in Button Layout. \n\n\n\nif set to `false` it hides the AudioModeButton in Button Layout\n\n\n\n**Default value = true** | 
| `showEndCallButton(boolean b)` | If set to `true` it displays the EndCallButton in Button Layout. \n\n\n\nif set to `false` it hides the EndCallButton in Button Layout\n\n\n\n**Default value = true** | 
| `showPauseVideoButton(boolean b)` | If set to `true` it displays the PauseVideoButton in Button Layout. \n\n\n\nif set to `false` it hides the PauseVideoButton in Button Layout\n\n\n\n**Default value = true** | 
| `showMuteAudioButton(boolean b)` | If set to `true` it displays the MuteAudioButton in Button Layout. \n\n\n\nif set to `false` it hides the MuteAudioButton in Button Layout\n\n\n\n**Default value = true** | 
| `showSwitchCameraButton(boolean b)` | If set to `true` it displays the SwitchCameraButton in Button Layout. \n\n\n\nif set to `false` it hides the SwitchCameraButton in Button Layout\n\n\n\n**Default value = true** | 
| `setAudioOnlyCall(boolean b)` | If set to true, the call will be strictly an audio call. If ser to false, the call will be an audio-video call.\n\n\n**Default value = false** | 
| `setMode(String mode)` | CometChat provides 3 options for the calling UI. \n\n\n\n1. CallSettings.MODE_DEFAULT\n2. CallSettings.MODE_SPOTLIGHT\n3. CallSettings.MODE_SINGLE\n\n\n**Default value = CallSettings.MODE_DEFAULT** | 
| `startWithAudioMuted(boolean b)` | This ensures the call is started with the audio muted if set to true | 
| `startWithVideoMuted(boolean b)` | This ensures the call is started with video paused if set to true | 
| `setDefaultAudioMode(String audioMode)` | This method can be used if you wish to start the call with a specific audio mode. The available options are \n\n\n\n1. CometChatConstants.AUDIO_MODE_SPEAKER = "SPEAKER"\n2. CometChatConstants.AUDIO_MODE_EARPIECE = "EARPIECE"\n3. CometChatConstants.AUDIO_MODE_BLUETOOTH = "BLUETOOTH"\n4. CometChatConstants.AUDIO_MODE_HEADPHONES = "HEADPHONES" | 
| `showSwitchToVideoCallButton(boolean showSwitchToVideoCallButton)` | This method shows/hides the switch to video call button. If set to true it will display the switch to video call button. If set to false it will hide the switch to video call button.\n\n\n\n**Default value = true** | 
| `setAvatarMode(String avatarMode)` | This method sets the mode of avatar. The avatar mode can be one of the below constants:\n\n\n\n1. CallSettings.AVATAR_MODE_CIRCLE\n2. CallSettings.AVATAR_MODE_SQUARE\n3. _CallSettings._AVATAR_MODE_FULLSCREEN\n\n\n**Default value = CallSettings.AVATAR_MODE_CIRCLE** | 
| setMainVideoContainerSetting(MainVideoContainerSetting containerSettings) | This method can be used to customize the main video container. You can read more about this [here](https://www.cometchat.com/docs/android-chat-sdk/video-view-customisation). | 
| `enableVideoTileClick(boolean enableVideoTileClick)` | This method can be used to enable/disable video tile click functionality in **Spotlight** mode.\n\n\n\n**Default value = true** | 
| `enableVideoTileDrag(boolean enableVideoTileDrag)` | This method can be used to enable/disable video tile drag functionality in **Spotlight** mode.\n\n\n\n**Default value = true** | 


In case you wish to achieve a completely customized UI for the Calling experience, you can do so by embedding default android buttons to the screen as per your requirement and then use the below methods to achieve different functionalities for the embedded buttons.

For the use case where you wish to align your own custom buttons and not use the default layout provided CometChat you can embed the buttons in your layout and use the below methods to perform the corresponding operations:

### Switch Camera

You can call `switchCamera()` Method to toggle between camera sources.

```java
CallManager callManager = CallManager.getInstance();
callManager.switchCamera();
```

```kotlin
val callManager: CallManager = CallManager.getInstance()
callManager.switchCamera()
```



### Mute Audio

You can call `muteAudio()` Method to mute your Audio Stream to the end-user.

```java
CallManager callManager = CallManager.getInstance();
callManager.muteAudio(true);
```

```kotlin
val callManager: CallManager = CallManager.getInstance()
callManager.muteAudio(true)
```



if set to `true` the Audio Stream is muted and if set to`false` Audio Stream is transmitted.

### Pause Video

You can call `pauseVideo()` Method to pause Video Stream to the end-user.

```java
CallManager callManager = CallManager.getInstance();
callManager.pauseVideo(true);
```

```kotlin
val callManager: CallManager = CallManager.getInstance()
callManager.pauseVideo(true)
```



if set to `true` the Video Stream is muted and if set to `false` Video Stream is transmitted.

### Set Audio Mode

You can call `setAudioMode()` to set the output of the audio stream.

```java
CallManager callManager = CallManager.getInstance();
String audioMode = CometChatConstants.AUDIO_MODE_EARPIECE;
callManager.setAudioMode(audioMode);
```

```kotlin
val callManager: CallManager = CallManager.getInstance()
val audioMode = CometChatConstants.AUDIO_MODE_EARPIECE
callManager.setAudioMode(audioMode)
```



The audio mode string can have either one of the below 4 values:

- AUDIO_MODE_SPEAKER = "SPEAKER"
- AUDIO_MODE_EARPIECE = "EARPIECE"
- AUDIO_MODE_BLUETOOTH = "BLUETOOTH"
- AUDIO_MODE_HEADPHONES= "HEADPHONES"

### End Call

You can use the `CometChat.endCall()` method of the `CometChat` class to end the call.

```java
CometChat.endCall("SESSION_ID_FOR_THE_CALL", new CometChat.CallbackListener<Call>() {
  @Override
  public void onSuccess(Call call) {
    __ handle end call success
  }

  @Override
  public void onError(CometChatException e) {
    __ handled end call error
  }

});
```

```kotlin
CometChat.endCall("SESSION_ID_FOR_THE_CALL", object : CallbackListener<Call?>() {
  override fun onSuccess(call: Call?) {
    __ handle end call success
  }

  override fun onError(e: CometChatException) {
    __ handled end call error
  }
})
```



### Get the list of available audio modes

This method will return the list of available audio modes. Based on the list received, you can set the audio mode for the ongoing call using the `setAudioMode()` method

```java
CallManager.getInstance().getAudioOutputModes(new CometChat.CallbackListener<List<AudioMode>>() {
  @Override
  public void onSuccess(List<AudioMode> audioModes) {
    Log.d(TAG, "Availabe audio modes received");                      
  }

  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "Error while fetching audio modes " + e.getMessage());
  }

});
```

```kotlin
CallManager.getInstance()
  .getAudioOutputModes(object : CallbackListener<List<AudioMode?>?>() {
    override fun onSuccess(audioModes: List<AudioMode?>?) {
      Log.d(TAG, "Availabe audio modes received")
    }

    override fun onError(e: CometChatException) {
      Log.d(TAG, "Error while fetching audio modes " + e.message)
    }
  })
```



The AudioMode class has the below properties:

1. mode - The mode can be either one of the below values:

- AUDIO_MODE_SPEAKER = "SPEAKER"
- AUDIO_MODE_EARPIECE = "EARPIECE"
- AUDIO_MODE_BLUETOOTH = "BLUETOOTH"
- AUDIO_MODE_HEADPHONES= "HEADPHONES"

2. isSelected - This is a boolean value that indicates if the audio mode is the active mode.

### Switch To Video Call

You can use the `switchToVideoCall()` method to switch from audio call to video call.

```java
CallManager.getInstance().switchToVideoCall();
```

```kotlin
CallManager.getInstance().switchToVideoCall()
```



> The `CometChat.getActiveCall()` method in case of Direct Calling will return null and all the details related to the call session will have to be saved and maintained at your end.

## Call Participant Count

In order to get the number of participants in any call, you can use the `getCallParticipantCount()` method. This method takes the session id for the call and returns the number or participants that are active in the call

```java
String sessionId = "abc";
String callType = CallSettings.CALL_MODE_DIRECT;

CometChat.getCallParticipantCount(sessionId, callType, new CometChat.CallbackListener<Integer>() {
  @Override
  public void onSuccess(Integer integer) {
    __ handle success
  }

  @Override
  public void onError(CometChatException e) {
    __ handle error
  }
});
```

```kotlin
val sessionId = "abc"
val callType = CallSettings.CALL_MODE_DIRECT

CometChat.getCallParticipantCount(sessionId, callType, object : CallbackListener<Int?>() {
  override fun onSuccess(integer: Int?) {
    __ handle success
  }

  override fun onError(e: CometChatException) {
    __ handle error
  }
})
```

