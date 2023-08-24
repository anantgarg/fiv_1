## Send a Typing Indicator

_In other words, as a sender, how do I let the recipient(s) know that I'm typing?_

### Start Typing

You can use the `startTyping()` method to inform the receiver that the logged in user has started typing. The receiver will receive this information in the `onTypingStarted()` method of the `MessageListener` class. In order to send the typing indicator, you need to use the `TypingIndicator` class.

```java
TypingIndicator typingIndicator = new TypingIndicator(UID, CometChatConstants.RECEIVER_TYPE_USER);

CometChat.startTyping(typingIndicator);
```

```kotlin
val typingIndicator =TypingIndicator(UID,CometChatConstants.RECEIVER_TYPE_USER)

CometChat.startTyping(typingIndicator)
```

```java
TypingIndicator typingIndicator = new TypingIndicator(GUID, CometChatConstants.RECEIVER_TYPE_GROUP);

CometChat.startTyping(typingIndicator);
```

```kotlin
val typingIndicator=TypingIndicator(GUID,CometChatConstants.RECEIVER_TYPE_GROUP)

CometChat.startTyping(typingIndicator)
```



### Stop Typing

You can use the `endTyping()` method to inform the receiver that the logged in user has stopped typing. The receiver will receive this information in the `onTypingEnded()` method of the `MessageListener` class. In order to send the typing indicator, you need to use the `TypingIndicator` class.

```java
TypingIndicator typingIndicator = new TypingIndicator(UID, CometChatConstants.RECEIVER_TYPE_USER);

CometChat.endtyping(typingIndicator);
```

```kotlin
val typingIndicator = TypingIndicator(UID,CometChatConstants.RECEIVER_TYPE_USER)
     
CometChat.endTyping(typingIndicator)
```

```java
TypingIndicator typingIndicator = new TypingIndicator(GUID, CometChatConstants.RECEIVER_TYPE_GROUP);

CometChat.endTyping(typingIndicator);
```

```kotlin
val typingIndicator=TypingIndicator(GUID,CometChatConstants.RECEIVER_TYPE_GROUP)

CometChat.endTyping(typingIndicator)
```



> You can use the `metadata` field of the `TypingIndicator` class to pass additional data along with the typing indicators. The metadata field is a JSONObject and can be set using the `setMetadata()` method of the `TypingIndicator` class. This data will be received at the receiver end and can be obtained using the `getMetadata()` method.

## Real-time Typing Indicators

_In other words, as a recipient, how do I know when someone is typing?_

You will receive the typing indicators in the `onTypingStarted()` and the `onTypingEnded()` method of the registered `MessageListener` class.

```java
CometChat.addMessageListener("Listener 1", new CometChat.MessageListener() {
  @Override
  public void onTypingStarted(TypingIndicator typingIndicator) {
    Log.d(TAG, " Typing Started : " + typingIndicator.toString());
  }

  @Override
  public void onTypingEnded(TypingIndicator typingIndicator) {
    Log.d(TAG, " Typing Ended : " + typingIndicator.toString());
  }

});
```

```kotlin
CometChat.addMessageListener("Listener 1",object :CometChat.MessageListener(){
  override fun onTypingEnded(typingIndicator: TypingIndicator?) {
    Log.d(TAG,"onTypingEnded: ${typingIndicator.toString()}")
  }

  override fun onTypingStarted(typingIndicator: TypingIndicator?) {
    Log.d(TAG,"onTypingStarted: ${typingIndicator.toString()}")
  }

})
```



The `TypingIndicator` class consists of the below parameters:

| Parameter | Information | 
| ---- | ---- | 
| `sender` | An object of the `User` class holding all the information related to the sender of the typing indicator. | 
| `receiverId` | `UID` of the receiver. This is the ID of the group or the user the typing indicator is being sent to. | 
| `receiverType` | This parameter indicates if the typing indicator is to be sent to a user or a group. The possible values are:\n\n\n\n1. `CometChatConstants.RECEIVER_TYPE_USER`\n2. `CometChatConstants.RECEIVER_TYPE_GROUP` | 
| `metadata` | A JSONObject to provider additional data | 
