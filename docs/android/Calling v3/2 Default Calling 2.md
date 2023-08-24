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



As mentioned in the [Overview](/cometchat-documentation/v3/android-chat-sdk/calling-default-calling) section, Once the call is initiated, there are three options that can be possible:

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

Once the call request is sent and the receiver has accepted the call, both the initiator and the receiver need to call the `startSession()` method. Starting call session is same as [Direct Call](/docs/android-chat-sdk/direct-calling-v3)