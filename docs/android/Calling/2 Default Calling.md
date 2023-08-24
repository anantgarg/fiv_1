This section will provide information on how a complete calling workflow can be set up using CometChat. We've built the complete workflow to help your users make calls, receive calls as well as accept/reject calls.

Let us assume Alex to be the call initiator and Bob is the receiver.

1. Alex initiates the call to Bob using the **initiateCall()** method.
2. Bob now has two choices:
    1. Accept the call from Alex using the **acceptCall()** method.
    2. Reject the call from Alex using the **rejectCall("rejected")** method passing the status as `rejected`.

3. In the meantime, Alex has the option to cancel the call he initiated to Bob using the **rejectCall("cancelled")** method passing the status as `cancelled`.
4. If Bob accepts the call from Alex, both Alex and Bob need to call the **startCall()** method. Alex in the **onOutgoingCallAccepted()** method of the `CallListener` and Bob in the success obtained from the `acceptCall()` method and both will be connected to each other.

## Initiate Call

The `initiateCall()` method sends a call request to a user or a group.

```java
private String receiverID = "UID";
private String receiverType = CometChatConstants.RECEIVER_TYPE_USER;
private String callType = CometChatConstants.CALL_TYPE_VIDEO;

Call call = new Call(receiverID, receiverType, callType);

CometChat.initiateCall(call, new CometChat.CallbackListener<Call>() {
  @Override
  public void onSuccess(Call call) {
    Log.d(TAG, "Call initiated successfully: " + call.toString());
  }
  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "Call initialization failed with exception: " + e.getMessage());
    
  }
});
```

```kotlin
val receiverID = "UID"
val receiverType = CometChatConstants.RECEIVER_TYPE_USER
val callType = CometChatConstants.CALL_TYPE_VIDEO

val call = Call(receiverID, receiverType, callType)

CometChat.initiateCall(call, object : CallbackListener<Call>() {
  override fun onSuccess(call: Call) {
    Log.d(TAG, "Call initiated successfully: " + call.toString())
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "Call initialization failed with exception: " + e.message)
  }
})
```

```java
private String receiverId = "GUID";
private String receiverType = CometChatConstants.RECEIVER_TYPE_GROUP;
private String callType = CometChatConstants.CALL_TYPE_VIDEO;

Call call = new Call(receiverId, receiverType, callType);

CometChat.initiateCall(call, new CometChat.CallbackListener<Call>() {
  @Override
  public void onSuccess(Call call) {
    Log.d(TAG, "Call initiated successfully: " + call.toString());
  }
  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "Call initialization failed with exception: " + e.getMessage());
  }
});
```

```kotlin
val receiverID:String="GUID"
val receiverType:String = CometChatConstants.RECEIVER_TYPE_GROUP
val callType:String = CometChatConstants.CALL_TYPE_VIDEO

val call=Call(receiverID,receiverType,callType)

CometChat.initiateCall(call,object :CometChat.CallbackListener<Call>(){
  override fun onSuccess(p0: Call?) {
    Log.d(TAG, "Call initiated successfully: " + p0?.toString())        
  }

  override fun onError(p0: CometChatException?) {
    Log.d(TAG, "Call initialization failed with exception: " + p0?.message)
  }
})
```



This method takes an object of the `Call` class. The constructor for `Call` class takes the following parameters:

| Parameter | Description | 
| ---- | ---- | 
| `receiverID` | The UID or GUID of the recipient | 
| `receiverType` | The type of the receiver viz.\n\n\n\n1.`CometChatConstants.RECEIVER_TYPE_USER`\n2.`CometChatConstants.RECEIVER_TYPE_GROUP` | 
| `callType` | The type of the call viz.\n\n\n\n1.`CometChatConstants.CALL_TYPE_AUDIO`\n2.`CometChatConstants.CALL_TYPE_VIDEO` | 


On successful initialization, a `Call` object is returned with the details of the call including a unique session ID for the call.

## Receive Calls

For every activity you wish to receive the call events in, you need to register the `CallListener` listener using the `addCallListener()` method.

```java
private String listenerId = "UNIQUE_LISTENER_ID";

CometChat.addCallListener(listenerId, new CometChat.CallListener() {
  @Override
  public void onIncomingCallReceived(Call call) {
    Log.d(TAG, "Incoming call: " +
          call.toString());
  }
  @Override
  public void onOutgoingCallAccepted(Call call) {
    Log.d(TAG, "Outgoing call accepted: " +
          call.toString());
  }
  @Override
  public void onOutgoingCallRejected(Call call) {
    Log.d(TAG, "Outgoing call rejected: " +
          call.toString());
  }
  @Override
  public void onIncomingCallCancelled(Call call) {
    Log.d(TAG, "Incoming call cancelled: " +
          call.toString());
  }

});
```

```kotlin
val listenerID:String="UNIQUE_LISTENER_ID"

CometChat.addCallListener(listenerID,object :CometChat.CallListener(){
  override fun onOutgoingCallAccepted(p0: Call?) {
    Log.d(TAG, "Outgoing call accepted: " + p0?.toString())
  }
  override fun onIncomingCallReceived(p0: Call?) {
    Log.d(TAG, "Incoming call: " + p0?.toString())
  }

  override fun onIncomingCallCancelled(p0: Call?) {
    Log.d(TAG, "Incoming call cancelled: " + p0?.toString())
  }

  override fun onOutgoingCallRejected(p0: Call?) {
    Log.d(TAG, "Outgoing call rejected: " + p0?.toString())
  }

})
```



| Parametrer | Description | 
| ---- | ---- | 
| `listenerID` | An ID that uniquely identifies that listener. We recommend using the activity or fragment name | 


We recommend you remove the listener once the activity or fragment is not in use.

```java
private String listenerId = "UNIQUE_LISTENER_ID";

CometChat.removeCallListener(listenerId);
```

```kotlin
val listenerID:String="UNIQUE_LISTENER_ID"

CometChat.removeCallListener(listenerID)
```



As mentioned in the [Overview](https://www.cometchat.com/docs/v3/android-chat-sdk/calling-default-calling) section, Once the call is initiated, there are three options that can be possible:

1. The receiver of the call accepts the call.
2. The receiver of the call rejects the call.
3. The initiator of the call cancels the call.

Please find below how these three scenarios can be implemented:

### Accept the Incoming Call

Once you have received an incoming call from a user or in any group, to accept the call using the `acceptCall()` method.

```java
private String sessionID = "SESSION_ID";

CometChat.acceptCall(sessionID, new CometChat.CallbackListener<Call>() {
  @Override
  public void onSuccess(Call call) {
    Log.d(TAG, "Call accepted successfully: " + call.toString());
  }
  public void onError(CometChatException e) {
    Log.d(TAG, "Call acceptance failed with exception: " + e.getMessage());
  }
});
```

```kotlin
val sessionID:String = "SESSION_ID"

CometChat.acceptCall(sessionID,object :CometChat.CallbackListener<Call>(){
  override fun onSuccess(p0: Call?) {
    Log.d(TAG, "Call accepted successfully: " + p0?.toString())
  }

  override fun onError(p0: CometChatException?) {
    Log.d(TAG, "Call acceptance failed with exception: " + p0?.message)

  }
})
```



| Parameter | Description | 
| ---- | ---- | 
| `sessionID` | The unique session ID available in the `Call` object | 


### Reject the Incoming Call

To reject the incoming call once it is received using the `rejectCall()` method.

```java
private String sessionID = "SESSION_ID";
private String status = CometChatConstants.CALL_STATUS_REJECTED;

CometChat.rejectCall(sessionID, status, new CometChat.CallbackListener<Call>() {
  @Override
  public void onSuccess(Call call) {
    Log.d(TAG, "Call rejected successfully with status: " +
          call.getCallStatus());
  }
  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "Call rejection failed with exception: " + e.getMessage());
  }
});
```

```kotlin
val sessionID:String = "SESSION_ID"
val status:String = CometChatConstants.CALL_STATUS_REJECTED

CometChat.rejectCall(sessionID,status,object:CometChat.CallbackListener<Call>(){
  override fun onSuccess(p0: Call?) {
    Log.d(TAG, "Call rejected successfully with status: " + p0?.callStatus)
  }

  override fun onError(p0: CometChatException?) {
    Log.d(TAG, "Call rejection failed with exception: " + p0?.message)
  }
})
```



| Parameter | Description | 
| ---- | ---- | 
| `sessionID` | The unique session ID available in the `Call` object | 
| `status` | Reason for rejection of the call | 


Here the status needs to be set as `CometChatConstants.CALL_STATUS_REJECTED` as the call is being rejected by the receiver of the call.

### Cancel the Outgoing Call

In the case where the initiator wishes to cancel the call, use the same above `rejectCall()` method and just pass the status to the `rejectCall()` method as `CometChatConstants.CALL_STATUS_CANCELLED`

## Start a Call

Once the call request is sent and the receiver has accepted the call, both the initiator and the receiver need to call the `startCall()` method.

You need to call this method for two scenarios:

1. After you accept an incoming call i.e. in the `onSuccess()` callback of the `acceptCall()` method.
2. After the recipient accepts an outgoing call i.e. in the `onOutgoingCallAccepted()` callback of the `CallListener` listener.

```java
String sessionID = "SESSION_ID";
RelativeLayout callView;
Activity activity;

CallSettings callSettings = new CallSettings.CallSettingsBuilder(activity,callView)
  .setSessionId(sessionId)
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
    Log.d(TAG, "onUserListUpdated: " + list.toString());
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

val callSettings = CallSettingsBuilder(activity, callView)
  .setSessionId(sessionId)
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



> The current `startCall()` method which takes the `activity`, `sessionId`, `relativeLayout to load the call view` parameters directly, is deprecated and will be replaced in the future versions. It will continue to work on this version but we suggest moving to the new method as shown above using the object of the `CallSettings` class as the parameter.

| Parameter | Description | 
| ---- | ---- | 
| `activity` | The activity that you want to show the calling view in. | 
| `sessionID` | The unique session ID available in the `Call` object | 
| `RelativeLayout` | An object of the relativeLayout class in which CometChat can load the calling views | 


The `OngoingCallListener` listener provides you with the below callback methods:

| Callback Method | Description | 
| ---- | ---- | 
| `onUserJoined(User user)` | This method is called when any other user joins the call. The user details can be obtained from the `User` object provided. | 
| `onUserLeft(User user)` | This method is called when a user leaves the call. The details of the user can be obtained from the provided `User` object. | 
| `onError()` | This method is called when there is some error in establishing the call. | 
| `onCallEnded()` | This method is called when the call is successfully ended. The call details can be obtained from the `Call` object provided. | 
| `onUserListUpdated(List<User> users)` | This method is triggered every time a participant joins or leaves the call providing the list of users active in the call | 
| `onAudioModesUpdated(List< audioModes>)` | This callback is triggered if any new audio output source is available or becomes unavailable. | 
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
| `startWithAudioMuted(boolean b)` | This ensures that the call is started with the audio muted if set to true. | 
| `startWithVideoMuted(boolean b)` | This ensures that the call is started with the video paused if set to true. | 
| `setDefaultAudioMode(String audioMode)` | This method can be used if you wish to start the call with a specific audio mode. The available options are \n\n\n\n1. CometChatConstants.AUDIO_MODE_SPEAKER = "SPEAKER"\n2. CometChatConstants.AUDIO_MODE_EARPIECE = "EARPIECE"\n3. CometChatConstants.AUDIO_MODE_BLUETOOTH = "BLUETOOTH"\n4. CometChatConstants.AUDIO_MODE_HEADPHONES = "HEADPHONES" | 
| `showSwitchToVideoCallButton(boolean showSwitchToVideoCallButton)` | This method shows/hides the switch to video call button. If set to true it will display the switch to video call button. If set to false it will hide the switch to video call button.\n\n\n\n**Default value = true** | 
| `setAvatarMode(String avatarMode)` | This method sets the mode of avatar. The avatar mode can be one of the below constants:\n\n\n\n1. CallSettings.AVATAR_MODE_CIRCLE\n2. CallSettings.AVATAR_MODE_SQUARE\n3. _CallSettings._AVATAR_MODE_FULLSCREEN\n\n\n**Default value = CallSettings.AVATAR_MODE_CIRCLE** | 
| `setMainVideoContainerSetting(MainVideoContainerSetting containerSettings)` | This method can be used to customize the main video container. You can read more about this [here](https://www.cometchat.com/docs/android-chat-sdk/video-view-customisation). | 
| `enableVideoTileClick(boolean enableVideoTileClick)` | This method can be used to enable/disable video tile click functionality in **Spotlight** mode.\n\n\n\n**Default value = true** | 
| `enableVideoTileDrag(boolean enableVideoTileDrag)` | This method can be used to enable/disable video tile drag functionality in **Spotlight** mode.\n\n\n\n**Default value = true** | 


In case you wish to achieve a completely customised UI for the Calling experience, you can do so by embedding default android buttons to the screen as per your requirement and then use the below methods to achieve different functionalities for the embedded buttons.

For the use case where you wish to align your own custom buttons and not use the default layout provided by CometChat you can embed the buttons in your layout and use the below methods to perform the corresponding operations:

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



if set to `true` the audio Stream is muted and if set to`false` the audio Stream is transmitted.

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



if set to `true` the video Stream is muted and if set to`false` video Stream is transmitted.

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



### Get list of available audio modes

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
CallManager.getInstance().getAudioOutputModes(object : CallbackListener<List<AudioMode?>?>() {
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



## Active Call

CometChat provides a method to get the details of the call that is currently active. The `CometChat.getActiveCall()` will return an object of the `Call` class containing the details of the ongoing call. If there is no ongoing call this method will return null.

```java
CallManager.getInstance().getActiveCall();
```

```kotlin
CallManager.getInstance().getActiveCall()
```



> The `getActiveCall()` method will only return the details of the active call for the ongoing session in which the call has been started. If the app is restarted, the data will be lost.

## Call Participant Count

In order to get the number of participants in any call, you can use the `getCallParticipantCount()` method. This method takes the session id for the call and returns the number or participants that are active in the call

```java
String sessionId = "abc";
String callType = CallSettings.CALL_MODE_DEFAULT;

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
val callType = CallSettings.CALL_MODE_DEFAULT

CometChat.getCallParticipantCount(sessionId, callType, object : CallbackListener<Int?>() {
  override fun onSuccess(integer: Int?) {
    __ handle success
  }

  override fun onError(e: CometChatException) {
    __ handle error
  }
})
```

